[TOC]

# Leetcode-Java

## 1.两数之和

```java
import java.util.HashMap;
import java.util.Map;

class Solution {
    public int[] twoSum(int[] nums, int target) {
        Map<Integer,Integer> map = new HashMap<Integer,Integer>();
        int[] res = new int[2];
        for(int i=0;i<nums.length;i++){
            if(map.containsKey(nums[i])){
                res[0] = map.get(nums[i]);
                res[1] = i;
                return res;
            }
            map.put(target-nums[i],i);
        }
        return res;
    }
}
```

## 2.两数相加

## 3.无重复字符的最长子串

## 4.寻找两个正序数组的中位数

## 5.最长回文子串

## 6.Z字形变换

## 7.整数反转

## 8.字符串转换整数（atoi）

## 9.回文数

## 10.正则表达式匹配

## 11.盛最多水的容器

## 12.整数转罗马数字

## 13.罗马数字转整数

## 14.最长公共前缀

## 15.三数之和

## 16.最接近的三数之和

## 17.电话号码的字母组合

## 18.四数之和

## 19.删除链表的倒数第N个结点

## 20.有效的括号

## 21.合并两个有序链表

## 22.括号生成

## 23.合并K个升序链表

## 24.两两交换链表中的节点

