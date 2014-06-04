---
layout: post
title: jekyll 2.0.3 | Error:  invalid byte sequence in US-ASCII
category: problems
---




###1. 执行jekyll server时，报如下的错：
	    ✗ jekyll serve
          Generating...
    jekyll 2.0.3 | Error:  invalid byte sequence in US-ASCII
    
###2. ruby版本是2.0
	✗ ruby -v
	ruby 2.0.0p451 (2014-02-24 revision 45167) [universal.x86_64-darwin13]
###3. jekyll版本是2.0.3
	✗ jekyll --version
	jekyll 2.0.3
###4.系统是os x10.9.3
###5.在stackoverflow网站上查了一上，answer is [here](http://stackoverflow.com/questions/3192128/invalid-byte-sequence-in-us-ascii-ruby-1-9-rails-2-3-8-mongodb-mongo-mapp) 
	cd $HOME
	vi .bashrc
	add locale conf below:

	export LANG="en_US.UTF-8"
	export LC_ALL="en_US.UTF-8"
	export LC_CTYPE=en_US.UTF-8
	save and run: source ~/.bashrc
在我机器上，是这样执行的：

	cd $HOME
	vim .zshrc
	add locale conf below:
	
	export LANG="en_US.UTF-8"
	export LC_ALL="en_US.UTF-8"
	export LC_CTYPE=en_US.UTF-8
	save and run: source ~/.zshrc

    ✗ sudo locale
    Password:
    LANG="en_US.UTF-8"
    LC_COLLATE="en_US.UTF-8"
    LC_CTYPE="en_US.UTF-8"
    LC_MESSAGES="en_US.UTF-8"
    LC_MONETARY="en_US.UTF-8"
    LC_NUMERIC="en_US.UTF-8"
    LC_TIME="en_US.UTF-8"
    LC_ALL="en_US.UTF-8"
    
Then check my locale by typing the following command

	 ✗ sudo locale
    Password:
    LANG="en_US.UTF-8"
    LC_COLLATE="en_US.UTF-8"
    LC_CTYPE="en_US.UTF-8"
    LC_MESSAGES="en_US.UTF-8"
    LC_MONETARY="en_US.UTF-8"
    LC_NUMERIC="en_US.UTF-8"
    LC_TIME="en_US.UTF-8"
    LC_ALL="en_US.UTF-8"
    
###6. 执行jekyll server时，还是报如下的错：
	    ✗ jekyll serve
          Generating...
    jekyll 2.0.3 | Error:  invalid byte sequence in US-ASCII

	
	
	







{% include references.md %}
