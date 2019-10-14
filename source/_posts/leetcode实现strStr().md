---
title: leetcode实现strStr()
date: 2019-10-14 23:07:00
tags: c++
---
##Leetcode
###题目
```bash
	实现 strStr() 函数。
	
	给定一个 haystack 字符串和一个 needle 字符串，在 haystack 字符串中找出 needle 字符串出现的第一个位置 (从0开始)。如果不存在，则返回  -1。
	
	示例 1:
	
	输入: haystack = "hello", needle = "ll"
	输出: 2
	示例 2:
	
	输入: haystack = "aaaaa", needle = "bba"
	输出: -1
	说明:
	
	当 needle 是空字符串时，我们应当返回什么值呢？这是一个在面试中很好的问题。
	
	对于本题而言，当 needle 是空字符串时我们应当返回 0 。这与C语言的 strstr() 以及 Java的 indexOf() 定义相符。
	
	来源：力扣（LeetCode）
	链接：https://leetcode-cn.com/problems/implement-strstr
	著作权归领扣网络所有。商业转载请联系官方授权，非商业转载请注明出处。
```
###题解
```bash
	
	class Solution {
	public:
	    int strStr(string haystack, string needle) 
	    {
	         if(needle.empty())
	            return 0;
	        
	        int i=0,j=0;
	        while(haystack[i]!='\0'&&needle[j]!='\0')//同时遍历比较，且这样的循环条件保证了needle中下标不会越界
	        {
	            if(haystack[i]==needle[j])
	            {
	                i++;
	                j++;
	            }
	            else
	            {
	                i=i-j+1;
	                j=0; //保证了每次needle都是从第一个元素开始比较
	            }
	        }
	        if(needle[j]=='\0')
	            return i-j;
	        
	        return -1;
	    }
	};

```