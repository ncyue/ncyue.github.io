---
title: leetcode最后一个单词的长度
date: 2019-10-14 23:13:00
tags: c++
---
##Leetcode

###题目
```bash

	给定一个仅包含大小写字母和空格 ' ' 的字符串，返回其最后一个单词的长度。
	
	如果不存在最后一个单词，请返回 0 。
	
	说明：一个单词是指由字母组成，但不包含任何空格的字符串。
	
	示例:
	
	输入: "Hello World"
	输出: 5
	
	来源：力扣（LeetCode）
	链接：https://leetcode-cn.com/problems/length-of-last-word
	著作权归领扣网络所有。商业转载请联系官方授权，非商业转载请注明出处。
```

###题解
```bash

	class Solution {
	public:
	    int lengthOfLastWord(string s) 
	    {
	        if(s.size()==0)//如果字符串长度为0 则说明单词不存在
	            return 0;
	        int j=0; //记录单词长度
	        for(int i = s.size()-1;i>=0;i--)
	        {
	           // if(s[i]>='a'&&s[i]<='z'||s[i]>='A'&&s[i]<='Z')
	            if(s[i]!=' ')//如果字符串中元素等于' '时则不执行
	                j++;
	            else
	                if(j>0) //因为可能存在在字符串的最后有一连串" "所以要确保单词存在时且长度大于0时才是正确的
	                    return j;//返回最后一个单词的长度
	        }
	        return j;
	    }
	};

```