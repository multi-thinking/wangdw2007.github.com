---
layout: post
title: 看看这道题怎么做 Python Code quiz
category: tech
---


[原文](http://www.alphasights.com/careers/apply/hong-kong/ruby-on-rails-developer)

A local variable named log contains an array of hashes with timestamped events like so:<br/>

	log = [
		{time: 201201, x: 2},
  		{time: 201201, y: 7},
  		{time: 201201, z: 2},
  		{time: 201202, a: 3},
  		{time: 201202, b: 4},
  		{time: 201202, c: 0}
	]
Please collapse the log by date into an array of hashes containing one entry per day

	[
		{time: 201201, x: 2, y: 7, z: 2},
		{time: 201202, a: 3, b: 4, c: 0},
	]
Ordering in the input is not defined. Ordering in the result is not important. Do not rely on the names of the hash keys other than :time. The field below executes your code in a Sandbox with $SAFE=4, so you can't define new classes, use global variables, etc.

原文如上，原题要求用Ruby实现，最近在学Python, 功能是实现了，总感觉代码写的不精细，效率有待提升：

    log = [{'time': 201201, 'x': 2},\
    {'time': 201201, 'y': 7},\
    {'time': 201201, 'z': 2},\
    {'time': 201202, 'a': 3},\
    {'time': 201202, 'b': 4},\
    {'time': 201202, 'c': 0}\
    ]
    
    timeCounts = []
    for index, dic in enumerate(log):
    	for key, value in dic.items():
    		if key == 'time':
    			timeCounts.append(value)
    
    newTimeCounts = []
    newTimeCounts = list(set(timeCounts))
    
    newArr = []
    for index, singleTime in enumerate(newTimeCounts):
    	singleDic = {}
    	for i, dic in enumerate(log):
    		if dic['time'] == newTimeCounts[index]:
    			for key, value in dic.items():
    				singleDic[key] = value
    				singleDic['time'] = newTimeCounts[index]
    	newArr.append(singleDic)
    
    for index, dic in enumerate(newArr):	
    	print dic



运行结果：<br/>

	{'y': 7, 'x': 2, 'z': 2, 'time': 201201}
	{'a': 3, 'c': 0, 'b': 4, 'time': 201202}

{% include references.md %}
