  
[TOC]  
  


# 计算机基础知识

## 数据结构与算法

### 数组

|题目名称| 通过答案|
|:-:|:-:|
|[三数之和](https://leetcode-cn.com/problems/3sum/)|https://leetcode-cn.com/submissions/detail/20640298/|
|[最接近的三数之和](https://leetcode-cn.com/problems/3sum-closest/)| https://leetcode-cn.com/submissions/detail/20653028/|
|[四数之和](https://leetcode-cn.com/problems/4sum/)| https://leetcode-cn.com/submissions/detail/20656392/|
|[求众数](https://leetcode-cn.com/problems/majority-element/)| https://leetcode-cn.com/submissions/detail/20656392/|
|[确实的第一个正数](https://leetcode-cn.com/problems/first-missing-positive/)| https://leetcode-cn.com/submissions/detail/20707657/|
|[缺失数字](https://leetcode-cn.com/problems/missing-number/)| https://leetcode-cn.com/submissions/detail/20707918/|
|[寻找重复数](https://leetcode-cn.com/problems/find-the-duplicate-number/)| https://leetcode-cn.com/submissions/detail/20772982/|
|[错误的集合](https://leetcode-cn.com/problems/set-mismatch/)| https://leetcode-cn.com/submissions/detail/20774721/|
|[螺旋矩阵](https://leetcode-cn.com/submissions/detail/21076746/)| https://leetcode-cn.com/submissions/detail/21016403/|
|[螺旋矩阵 II](https://leetcode-cn.com/problems/spiral-matrix-ii/)| https://leetcode-cn.com/submissions/detail/20918082/|
|[数组中的第k个最大元素](https://leetcode-cn.com/problems/kth-largest-element-in-an-array/)| https://leetcode-cn.com/submissions/detail/21011260/|



### 链表
|题目名称| 通过答案|
|:-:|:-:|
|[环形链表](https://leetcode-cn.com/problems/linked-list-cycle/)| https://leetcode-cn.com/submissions/detail/20786910/ |
|[合并k个有序链表](https://leetcode-cn.com/problems/merge-k-sorted-lists/)| https://leetcode-cn.com/submissions/detail/20790855/ |

### 数学
|题目名称| 通过答案|
|:-:|:-:|
|[丑数](https://leetcode-cn.com/problems/ugly-number/)| https://leetcode-cn.com/submissions/detail/20795679/|
|[丑数II](https://leetcode-cn.com/problems/ugly-number-ii/)| https://leetcode-cn.com/submissions/detail/20796886/|
|[计数质数](https://leetcode-cn.com/problems/count-primes/)| https://leetcode-cn.com/submissions/detail/20796704/|
|[快乐数](https://leetcode-cn.com/problems/happy-number/)| https://leetcode-cn.com/submissions/detail/20796231/|


### 二分查找
|题目名称| 通过答案|
|:-:|:-:|
|[在排序数组中查找元素的第一个和最后一个位置](https://leetcode-cn.com/problems/find-first-and-last-position-of-element-in-sorted-array/)| https://leetcode-cn.com/submissions/detail/21272419/|
|[x 的平方根](https://leetcode-cn.com/problems/sqrtx/)| https://leetcode-cn.com/submissions/detail/21317327/|
|[两数之和 II - 输入有序数组](https://leetcode-cn.com/problems/two-sum-ii-input-array-is-sorted/)| https://leetcode-cn.com/submissions/detail/21646086/|
|[寻找两个有序数组的中位数](https://leetcode-cn.com/problems/median-of-two-sorted-arrays/)| https://leetcode-cn.com/submissions/detail/21670921/|
|[搜索旋转排序数组](https://leetcode-cn.com/problems/search-in-rotated-sorted-array/)| https://leetcode-cn.com/submissions/detail/21678251/|
|[搜索旋转排序数组 II](https://leetcode-cn.com/problems/search-in-rotated-sorted-array-ii/)| https://leetcode-cn.com/submissions/detail/21681374/|
|[寻找旋转排序数组中的最小值](https://leetcode-cn.com/problems/find-minimum-in-rotated-sorted-array/)|https://leetcode-cn.com/submissions/detail/21716749/|
|[寻找旋转排序数组中的最小值 II](https://leetcode-cn.com/problems/find-minimum-in-rotated-sorted-array-ii/)|https://leetcode-cn.com/submissions/detail/21717685/|

<details> <summary>查找第一个值等于给定值的元素</summary>

``` c++
/**
 * 二分查找，查找第一个值等于给定值的元素
 **/
 int binary_search_first(const vector<int>& nums, int target) {
     int left = 0;
     int right = nums.size() - 1;
     while (left <= right) {
         int mid = left + ((right - left) >> 1);
         if (nums[mid] > target) {
             right = mid - 1;
         } else if (nums[mid] < target) {
             left = mid + 1;
         } else {
             if (mid == 0 || nums[mid-1] != target) {
                 return mid;
             }
             right = mid - 1;
         }
     }
     return -1;
 }
```
</details>

<details> <summary>查找最后一个值等于给定值的元素 </summary>

``` c++
/**
 * 二分查找，查找最后一个值等于给定值的元素
 **/
int binary_search_last(const vector<int>& nums, int target) {
    int left = 0;
    int right = nums.size() - 1;
    
    while (left <= right) {
        int mid = left + ((right-left)>>1);
        if (nums[mid] > target) {
            left = mid + 1;
        } else if (nums[mid] < target) {
            right = mid - 1;
        } else {
            if (mid == (nums.size() - 1) || nums[mid+1] != target) {
                return mid;
            }
            left = mid + 1;
        }
    }
    return -1;
}

```
</details>

<details> <summary>查找第一个大于等于给定值的元素 </summary>
  
``` c++
int binary_search(const vector<int>& nums, int target) {
    int left = 0;
    int right = nums.size() - 1
    while (left <= right) {
        int mid = left + ((right - left)>>1);
        if (nums[mid] >= target) {
            if (mid == 0 || nums[mid-1] < target) {
                return mid;
            }
            right = mid - 1;
        } else {
            left = mid + 1;
        }
    }
    return -1;
}
```
</details>

 <details> <summary>查找最后一个小于等于给定值的元素</summary>

``` cpp
/**
 * 二分查找，查找最后一个小于等于给定值的元素
 **/
 int binary_search(const vector<int>& nums, int target) {
     int left = 0;
     int right = nums.size() - 1;

     while (left <= right) {
         int mid = left + ((right - left)>>1);
         if (nums[mid] <= target) {
             if (mid == (nums.size()-1) || nums[mid+1]>target) {
                 // mid已经在最右边或者mid的下一个数字已经大于target的时候，
                 // 说明mid已经是最后一个小于等于target的下标
                 return mid;
             } else {
                 left = mid + 1;
             }
         } else {
             right = mid - 1;
         }
     }
     return -1;
 }
 ```
 </details>

### 二叉树
|题目名称| 通过答案|
|:-:|:-:|
|[二叉树的最大深度](https://leetcode-cn.com/problems/maximum-depth-of-binary-tree/)| https://leetcode-cn.com/submissions/detail/21302964/|
|[二叉树的最近公共祖先](https://leetcode-cn.com/problems/lowest-common-ancestor-of-a-binary-search-tree/)| https://leetcode-cn.com/submissions/detail/21349067/|
|[翻转二叉树](https://leetcode-cn.com/problems/invert-binary-tree/)| https://leetcode-cn.com/submissions/detail/21460764/|
|[验证二叉搜索树](https://leetcode-cn.com/problems/validate-binary-search-tree/)| https://leetcode-cn.com/submissions/detail/21463591/|
|[路径总和](https://leetcode-cn.com/problems/path-sum/)| https://leetcode-cn.com/submissions/detail/21464272/|
|[路径总和II](https://leetcode-cn.com/problems/path-sum-ii/)| https://leetcode-cn.com/submissions/detail/21464937/|
|[两数之和 IV - 输入 BST](https://leetcode-cn.com/problems/two-sum-iv-input-is-a-bst/)| https://leetcode-cn.com/submissions/detail/21647236/|
### 栈
|题目名称| 通过答案|
|:-:|:-:|
|[有效的括号](https://leetcode-cn.com/problems/valid-parentheses/)| https://leetcode-cn.com/submissions/detail/20865280/|
|[最长有效括号](https://leetcode-cn.com/problems/longest-valid-parentheses/)| https://leetcode-cn.com/submissions/detail/21256393/ |
|[最小栈](https://leetcode-cn.com/problems/min-stack/)| https://leetcode-cn.com/submissions/detail/21146151/|
|[逆波兰表达式求值](https://leetcode-cn.com/problems/evaluate-reverse-polish-notation/)| https://leetcode-cn.com/submissions/detail/20870427/|

### 队列
|题目名称| 通过答案|
|:-:|:-:|
|[设计循环双端队列](https://leetcode-cn.com/problems/design-circular-deque/)| https://leetcode-cn.com/submissions/detail/21008746/|

### 堆
|题目名称| 通过答案|
|:-:|:-:|
|[滑动窗口的最大值](https://leetcode-cn.com/problems/sliding-window-maximum/)| https://leetcode-cn.com/submissions/detail/21146151/|

### 动态规划
|题目名称| 通过答案|
|:-:|:-:|
|[爬楼梯](https://leetcode-cn.com/problems/climbing-stairs/)| https://leetcode-cn.com/submissions/detail/21076746/|

### 回溯算法
|题目名称| 通过答案|
|:-:|:-:|
|[全排列](https://leetcode-cn.com/problems/permutations/)| https://leetcode-cn.com/submissions/detail/20937974/|

### 字符串
|题目名称| 通过答案|
|:-:|:-:|
|[反转字符串 II](https://leetcode-cn.com/problems/reverse-string-ii/)| https://leetcode-cn.com/submissions/detail/21341242/|
|[反转字符串中的单词 III](https://leetcode-cn.com/problems/reverse-words-in-a-string-iii/)| https://leetcode-cn.com/submissions/detail/21350937/|
|[翻转字符串里的单词](https://leetcode-cn.com/problems/reverse-words-in-a-string/)| https://leetcode-cn.com/submissions/detail/21413670/|
|[字符串转换整数 (atoi)](https://leetcode-cn.com/problems/string-to-integer-atoi/)| https://leetcode-cn.com/submissions/detail/21431133/|

### 排序算法
------------------------------
| 名字 | 时间复杂度| 稳定性 | 原地排序(空间复杂度为O(1))|
|:-:   |:-:      |:-:    | :-: |
|快速排序| O(n*log(n)) | 不稳定 | 否 |
|归并排序| O(n*log(n)) | 稳定   | 否 |
|堆排序  | O(n*log(n)) | 不稳定 | 是 |
|插入排序| O(n*n)     | 稳定   | 是 |
|冒泡排序| O(n*n)     | 稳定   | 是 |
|选择排序| O(n*n)     | 不稳定 | 是 |
|桶排序 | O(n)        | 稳定   | 否 |

------------------------------

* 快速排序
* 归并排序
* 堆排序
* 插入排序
* 冒泡排序
* 选择排序
* 桶排序


## 操作系统

## 计算机网络

### 第3讲 —— ifconfig
![网络地址分类](网络地址分类.jpg)  
![分类地址数量](分类地址数量.jpg)

#### 无类型域间选路（CIDR） 

于是有了一个折中的方式叫作无类型域间选路,简称 CIDR 。这种方式打破了原来设计的几类地址
的做法,将 32 位的 IP 地址一分为二,前面是网络号,后面是主机号。从哪里分呢?你如果注意
观察的话可以看到, 10.100.122.2/24 ,这个 IP 地址中有一个斜杠,斜杠后面有个数字 24 。这种
地址表示形式,就是 CIDR 。后面 24 的意思是, 32 位中,前 24 位是网络号,后 8 位是主机
号。  
伴随着 CIDR 存在的,一个是广播地址, 10.100.122.255 。如果发送这个地址,所有 10.100.122
网络里面的机器都可以收到。另一个是子网掩码, 255.255.255.0 。  
将子网掩码和 IP 地址进行 AND 计算。前面三个 255 ,转成二进制都是 1 。 1 和任何数值取
AND ,都是原来数值,因而前三个数不变,为 10.100.122 。后面一个 0 ,转换成二进制是 0 , 0
和任何数值取 AND ,都是 0 ,因而最后一个数变为 0 ,合起来就是 10.100.122.0 。这就是网络
号。将子网掩码和 IP 地址按位计算 AND ,就可得到网络号。

#### 总结
* IP是地址，有定位功能；MAC是身份证，无定位功能；  
* CIDR可以用来判断是不是本地人
* IP分公有的IP和私有的IP。


### 第4讲 —— DHCP与PXE

#### DHCP (Dynamic Host Configuration Protocol), 动态主机分配协议: 网络中主机的网络自动配置协议，包括CIDR,子网掩码，广播地址和网关地址等。

* DHCP工作方式: DHCP Discover->DHCP Offer

* IP 地址的收回和续租  
客户机会在租期过去 50% 的时候，直接向为其提供 IP 地址的 DHCP Server 发送 DHCP request
消息包。客户机接收到该服务器回应的 DHCP ACK 消息包，会根据包中所提供的新的租期以及
其他已经更新的 TCP/IP 参数，更新⾃⼰的配置。这样，IP 租⽤更新就完成了。

#### PXE 预启动执行环境（Pre-boot Execution Environment）

* 工作过程  

![pxe工作过程](pxe工作过程.jpg)  


### 第5讲 —— 从物理层到MAC层(数据链路层)

## 数据库

## 计算机组成原理

<details> <summary>1. 原码 </summary>

``` 

原码就是符号位加上真值的绝对值, 即用第一位表示符号, 其余位表示值. 比如如果是8位二进制:

[+1]原 = 0000 0001

[-1]原 = 1000 0001

第一位是符号位. 因为第一位是符号位, 所以8位二进制数的取值范围就是:

[1111 1111 , 0111 1111]

即

[-127 , 127]

原码是人脑最容易理解和计算的表示方式.
```
</details>

<details> <summary>2. 反码 </summary>

```
反码的表示方法是:

正数的反码是其本身

负数的反码是在其原码的基础上, 符号位不变，其余各个位取反.

[+1] = [00000001]原 = [00000001]反

[-1] = [10000001]原 = [11111110]反

可见如果一个反码表示的是负数, 人脑无法直观的看出来它的数值. 通常要将其转换成原码再计算.
```

</details>

<details> <summary>3. 补码 </summary>

```
补码的表示方法是:

正数的补码就是其本身

负数的补码是在其原码的基础上, 符号位不变, 其余各位取反, 最后+1. (即在反码的基础上+1)

[+1] = [00000001]原 = [00000001]反 = [00000001]补

[-1] = [10000001]原 = [11111110]反 = [11111111]补

对于负数, 补码表示方式也是人脑无法直观看出其数值的. 通常也需要转换成原码在计算其数值.
```

</details>

<details> <summary>4. 为何要使用原码，反码和补码 </summary>

```
现在我们知道了计算机可以有三种编码方式表示一个数. 对于正数因为三种编码方式的结果都相同:

[+1] = [00000001]原 = [00000001]反 = [00000001]补

所以不需要过多解释. 但是对于负数:

[-1] = [10000001]原 = [11111110]反 = [11111111]补

可见原码, 反码和补码是完全不同的. 既然原码才是被人脑直接识别并用于计算表示方式, 为何还会有反码和补码呢?

首先, 因为人脑可以知道第一位是符号位, 在计算的时候我们会根据符号位, 选择对真值区域的加减. (真值的概念在本文最开头). 但是对于计算机, 加减乘数已经是最基础的运算, 要设计的尽量简单. 计算机辨别"符号位"显然会让计算机的基础电路设计变得十分复杂! 于是人们想出了将符号位也参与运算的方法. 我们知道, 根据运算法则减去一个正数等于加上一个负数, 即: 1-1 = 1 + (-1) = 0 , 所以机器可以只有加法而没有减法, 这样计算机运算的设计就更简单了.

于是人们开始探索 将符号位参与运算, 并且只保留加法的方法. 首先来看原码:

计算十进制的表达式: 1-1=0

1 - 1 = 1 + (-1) = [00000001]原 + [10000001]原 = [10000010]原 = -2

如果用原码表示, 让符号位也参与计算, 显然对于减法来说, 结果是不正确的.这也就是为何计算机内部不使用原码表示一个数.

为了解决原码做减法的问题, 出现了反码:

计算十进制的表达式: 1-1=0

1 - 1 = 1 + (-1) = [0000 0001]原 + [1000 0001]原= [0000 0001]反 + [1111 1110]反 = [1111 1111]反 = [1000 0000]原 = -0

发现用反码计算减法, 结果的真值部分是正确的. 而唯一的问题其实就出现在"0"这个特殊的数值上. 虽然人们理解上+0和-0是一样的, 但是0带符号是没有任何意义的. 而且会有[0000 0000]原和[1000 0000]原两个编码表示0.

于是补码的出现, 解决了0的符号以及两个编码的问题:

1-1 = 1 + (-1) = [0000 0001]原 + [1000 0001]原 = [0000 0001]补 + [1111 1111]补 = [0000 0000]补=[0000 0000]原

这样0用[0000 0000]表示, 而以前出现问题的-0则不存在了.而且可以用[1000 0000]表示-128:

(-1) + (-127) = [1000 0001]原 + [1111 1111]原 = [1111 1111]补 + [1000 0001]补 = [1000 0000]补

-1-127的结果应该是-128, 在用补码运算的结果中, [1000 0000]补 就是-128. 但是注意因为实际上是使用以前的-0的补码来表示-128, 所以-128并没有原码和反码表示.(对-128的补码表示[1000 0000]补算出来的原码是[0000 0000]原, 这是不正确的)

使用补码, 不仅仅修复了0的符号以及存在两个编码的问题, 而且还能够多表示一个最低数. 这就是为什么8位二进制, 使用原码或反码表示的范围为[-127, +127], 而使用补码表示的范围为[-128, 127].

因为机器使用补码, 所以对于编程中常用到的32位int类型, 可以表示范围是: [-231, 231-1] 因为第一位表示的是符号位.而使用补码表示时又可以多保存一个最小值.
```

</details>



# 语言相关的基础知识
