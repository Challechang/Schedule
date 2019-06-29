  
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

## 数据库

# 语言相关的基础知识
