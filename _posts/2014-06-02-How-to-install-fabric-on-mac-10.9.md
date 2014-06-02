---
layout: post
title: How to install fabric on mac 10.9
category: notes
---


[官网](http://www.fabfile.org/)<br/>

###1. What is Fabric?<br/>
Fabric is a Python (2.5-2.7) library and command-line tool for streamlining the use of SSH for application deployment or systems administration tasks.
###2. I try to install fabric on my mac 10.9.2, But I got failed. The steps are as follows:
1. Follows the steps on the page:http://docs.fabfile.org/en/1.8/installation.html
2. ~# pip install fabric
3. ~# fab
bash: fab: command not found

###3.After perform these steps, it works!
1. sudo find / | grep “fab”
I found fab executable is on "/Library/Frameworks/Python.framework/Versions/2.7/bin”
2. Put the fab executable into PATH
3. ~$ fab
Fatal error: Couldn't find any fabfiles!

####Remember that -f can be used to specify fabfile path, and use -h for help.


{% include references.md %}
