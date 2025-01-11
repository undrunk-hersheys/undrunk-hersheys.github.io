---
layout: post
title:  "How to make github blog "
date:   2025-01-10 16:42:10 +0900
categories: programming
---

This is the first blog post for this github blog.  
And I will post down how to make github blog.  

### What is Github Blog?
In the github, web files like html are hosted for free. This is Github Page. And by which is used by Github Page ius Github Blog. 

### How to make Github Page
To make Github Blog, Github Page needs to be set up first. Create new repository with the name of own username. (username.github.io) e.g.)undrunk-hersheys.github.io like image below.  

![GitHub IO](https://raw.githubusercontent.com/undrunk-hersheys/undrunk-hersheys.github.io/main/_posts/2025-01-10/github_io.png){:.ioda}

Go to the settings of username.github.io's repository -> pages. 

![Settings Pages](https://raw.githubusercontent.com/undrunk-hersheys/undrunk-hersheys.github.io/main/_posts/2025-01-10/settings_pages.png){:.ioda}

You will see Source with save button. Click on that Save buttons and your website will be published. It may take about max 10 minutes long especially when it is publishing for the first time.  

In the terminal clone the repository. (If first time using git, download git first.  
for windows https://git-scm.com/  
for linux sudo apt install git)  

```
git clone https://github.com/undrunk-hersheys/undrunk-hersheys.github.io.git
```

And go the local cloned directory and make index.html file. This is just for the test so make random words in here.  

```
<html>
	<body>
		==Github Blog==
	</body>
</html>
```
And push to the main branh.

```
git add .
git commit -m "github_blog_test"
git push origin main
```

And see if it works.  
This is the simple test for the github blog and now wil go on github theme. First we need Ruby and Jekyll. But before that we need to choose which theme that will be used in blog. Since every theme may require different version of the Ruby or Jekyll, (we can upgrade but since that is bothering for bit, but will explain about this too).  

### Applying Theme
You mayu choose any theme in http://jekyllthemes.org/. or https://github.com/topics/jekyll-theme. Or just google it whatever you like. For my undrunk-hersheys github blog, I chose the no-style-please. https://github.com/riggraz/no-style-please. Every theme is little different but overall they are alike. Choose the right theme for you.  

#### Installing Ruby
And install Ruby. Jekyll is made of Ruby so install Ruby first. Go to Ruby installer page and install the Ruby with Devkit. For me I had to download 3.4.1 version for my theme so please look after the README or usage section that describes about. https://rubyinstaller.org/downloads/. When it is intalled, open Start Command Prompt with Ruby. Just search file on windows, but if you wish to open specific version fo the ruby it may locate in the place below.  C:\Users\username\AppData\Roaming\Microsoft\Windows\Start Menu\Programs\Ruby 3.4.1-1-x64.

When open the terminal, you will see the black terminal window, type  
```
chcp 65001 
```
for encoding into UTF-8.
And go to the local clone repository of the github.io.

cd (your_repository_location)

And install Jekyll by 
```
gem install jekyll bundler
gem install webrick
jekyll new ./ --force
```
(this --force overwrite the repository
but since we only got .git, README and one example html file it is warning is unnecessary)  
```
bundle install
bundle exec jekyll serve
```
This make the local server for website, so go to http://127.0.0.1:4000/ (for the no-style-please you need to change the _config.yml baseurl to "/no-style-please" -> "")  
If the page look same of .html, it has worked successfully.

To apply the demo page, clone the theme from the github or donwload compressed file. For the compressed file you just need to copy and paste all the files and overwrite all the folders to local io directory.  
For the cloning, github, clone in the local io directory and move everything except for .git file(this is hidden file so View->Show/Hide->HIdden items). Delete .git of the cloned theme (not github.io repos' .git file). And then cut and paste all other files to github.io repository.   
Try the same command here and see if the theme has worked well.  
```
bundle install
bundle exec jekyll serve
```
If http://127.0.0.1:4000/ works coreectly as the Demo page, then it has worked successfully.  

```
git add .
git commit -m "Demo page"
git push origin main
```
It will take about 10 minutes to upload first jekyll.

And see if this works on the server.  
Go to https://username.github.io/  
for me https://undrunk-hersheys.github.io/  
and see it works same.  

### Cutomize
Change the _config.yml to your informations.  
And other data files are different on which theme you have chosen.  




