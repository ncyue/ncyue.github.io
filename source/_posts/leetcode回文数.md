---
title: leetcode回文数
date: 2019-10-6 20:10:00
tags: c++
---

## Leetcode

### 回文数



``` bash

	class Solution {
	public:
	    bool isPalindrome(int x) 
	    {
	        int k=0;//存储后半部分数字的反转结果
	        
	        if(x<0||(x%10==0&&x!=0))//排除负数和最后一位数字为0的数字
	            return false;
	        while(x>k)
	        {
	            k = k*10+x%10;
	            x/=10;
	        }
	        return k==x || k/10==x;//数字个数为偶数和奇数分两种情况
	    }
	    }；
```