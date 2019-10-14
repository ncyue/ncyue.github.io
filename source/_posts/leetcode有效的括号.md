---
title: leetcode有效的括号
date: 2019-10-14 23:03:00
tags: c++
---
```bash


	class Solution {
	public:
	    bool isValid(string s)
	    {
	        stack<char> sta;
	        for(const auto& v : s) //范围for
	        {
	            if(sta.empty()) //如果栈为空 在栈底添加元素v
	                sta.push(v);
	            else if(compare(sta.top(),v))//如果栈不为空，将元素v与栈顶元素比较
	                sta.pop(); //如果栈顶元素与元素v是相匹配的闭合括号，就删除栈顶元素             
	            else
	                sta.push(v);//如果不匹配将元素v入栈
	        }
	        return sta.size()==0 ? true : false;
	    }
	private:
	    bool compare(const char& c1,const char& c2)
	    {
	        return (c1 == '(' && c2 == ')') || (c1 == '[' && c2 == ']') || (c1 == '{' && c2 == '}');
	    }
	};


```