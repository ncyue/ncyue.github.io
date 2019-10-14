---
title: leetcode实现数组加一的操作
date: 2019-10-14 23:01:00
tags: c++
---
```bash



	class Solution {
	public:
	    vector<int> plusOne(vector<int>& digits) 
	    {       
	        for(int i = digits.size()-1;i>=0;i--)  
	        {
	            digits[i]++; //加一
	            digits[i]=digits[i]%10;//取余数
	            if(digits[i]!=0)//其实也就是当对应下标元素值不为9时 返回数组
	                return digits;
	        }//如果数组中全部为9 循环结束时 数组中元素全为0 
	        digits.push_back(0);//在容器尾部添加0
	        digits[0] = 1;
	        return digits;
	    }
	};
	
	/* 存在9的几种情况 :          1.当末位只有一个9
	                             2.不连续的9
	                             3.后边有连续的9
	                             4.全是9 */

```