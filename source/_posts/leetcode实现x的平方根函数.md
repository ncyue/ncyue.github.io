---
title: leetcode实现x的平方根函数
date: 2019-10-14 22:55:00
tags: c++
---
```bash
  	 	



	class Solution {
		public:
	   	 int mySqrt(int x) 
	    {
	        if(x==0)
	            return 0;
	        long left = 1;
	        long right = x/2+1;// # 为了照顾到 1 把右边界设置为 x // 2 + 1
	        
	        while(left<right)
	        {
	            // 注意：这里一定取右中位数，如果取左中位数，代码会进入死循环
	            // long mid = left + (right - left + 1) / 2;
	            long mid = (left+right+1) >> 1;  //mid一定要在循环体内 不然无法重置mid的值  
	            if(mid*mid>x)
	            {
	                right = mid-1;
	            }
	            else
	            {
	                left = mid;
	            }
	        }
	        // 因为一定存在，因此无需后处理
	        return (int)left;        
	    }
	};

```
