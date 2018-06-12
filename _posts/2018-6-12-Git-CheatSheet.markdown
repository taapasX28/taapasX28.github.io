---
title:  "Git CheatSheet"
subtitle: "A quick overview"
author: "Taapas Agrawal"
avatar: "img/authors/taapas.jpg"
image: "img/git.png"
date:   2018-06-12(Reading time 4 minutes) 12:12:12
---
**Git(DVCS)**

#### []()**What is Git?**

[]()From [Git’s](https://git-scm.com/)
official website:

Git is a [free
and open source](https://git-scm.com/about/free-and-open-source) distributed version control system designed to
handle everything from small to very large projects with speed and
efficiency.

**About Version Control**

What is version control, and why
should you care? Version control is a system that records changes to
a file or set of files over time so that you can recall specific
versions later. Even though the examples in this book show software
source code as the files under version control, in reality any type
of file on a computer can be placed under version control.

**Git install**
{% highlight ruby %}
sudo apt-get install git
{% endhighlight %}
**To check version:**
{% highlight ruby %}
git -- version
{% endhighlight %}
**For configuring:**
{% highlight ruby %}
git config -- global <keyword> “<Data>”
<keyword>=
1.user.name
2.user.email
3.core.editor
{% endhighlight %} etc.

To display current saved config type --&gt; {% highlight ruby %}git config --list{% endhighlight %}

**For help:**
{% highlight ruby %}
git help <verb>
{% endhighlight %}
eg: {% highlight ruby %}git help config{% endhighlight %} 
for help regarding configration process

**Creating a local repository:**

cd into the directory you want to track and simply type
{% highlight ruby %}
git -init 
{% endhighlight %}
this will create a .git file in the directory with a basic skeleton without any commits.

**To check which files can be commited:**
{% highlight ruby %}
git status 
{% endhighlight %}
this will list the files that can be commited 

- to ignore files create a .gitignore file using {% highlight ruby %} touch .gitignore {% endhighlight %} 
- open this  using text editor and add names of files you want to ignore 

**Moving files to staging area**

For adding files individually use --&gt; {% highlight ruby %}git add <filename>{% endhighlight %}

For adding all files at once use --&gt; {% highlight ruby %}git add -A{% endhighlight %}

To remove files from staging area use --&gt;{% highlight ruby %} git reset <filename>{% endhighlight %} 
and to remove all simply--&gt;{% highlight ruby %}git reset{% endhighlight %}

**To commit the files**

{% highlight ruby %}git commit{% endhighlight %}

but it is necessary to add messages with the commit to make sure what we did ; so for that we
use “-m” extension like
{% highlight ruby %}
git commit -m “message”
{% endhighlight %}
**To check the commit history**
{% highlight ruby %}
git log 
{% endhighlight %}
**Cloning a repository from internet**
{% highlight ruby %}
git clone <url> <location>
{% endhighlight %}
To clone into current directory use “.” in place of location

To check status of the cloned repository 
{% highlight ruby %}
git remote -v  {% endhighlight %}--&gt;
gives the location from where it is fetched 
{% highlight ruby %}
git  branch -a {% endhighlight %}--&gt;
gives all the branches 

**Changing and submitting:**

Make changes to the file of the cloned repository.Now to see change made type--&gt; 
{% highlight ruby %}
git diff
{% endhighlight %}
This will display the change made.

Now git status will view the modified file . 

Add the file to the staging area using git add -A

Commit these files with appropriate message .

Now before pushing it back . We need to pull and check whether any other person made a
change in the branch since the last time type in --&gt; 
{% highlight ruby %}git pull origin master{% endhighlight %}(If on master branch else use branchname in place of master)

Now for finally pushing type in --&gt;
{% highlight ruby %} 
git push origin master
{% endhighlight %}
**Branching:**

-
	To create a new branch--&gt; {% highlight ruby %}git branch <branchname>{% endhighlight %} 
- 
	To check all the branches present --&gt; {% highlight ruby %}git branch{% endhighlight %} 
- 
	To switch over branch --&gt; {% highlight ruby %}git checkout <branchname> {% endhighlight %}
- 
	to push a commited change --&gt;{% highlight ruby %} git push -u origin <branchname> {% endhighlight %}

**To merge the branch to master**

- 
	{% highlight ruby %}git merge <branchname> {% endhighlight %}
- 
	 To push the changes we simply use --&gt;{% highlight ruby %} git push origin master{% endhighlight %} 
- 
	To check it they are merged type in --&gt;{% highlight ruby %} git branch – merged {% endhighlight %}
- 
	if the branch is successfully merged we can now delete the branch--&gt;
	{% highlight ruby %}git branch -d <branchname>{% endhighlight %} 

**For Reference :**

Basic git
:[https://www.youtube.com/watch?v=HVsySz-h9r4&t=464s](https://www.youtube.com/watch?v=HVsySz-h9r4&t=464s)

Resolving a pull request:
[https://help.github.com/articles/resolving-a-merge-conflict-using-the-command-line/](https://help.github.com/articles/resolving-a-merge-conflict-using-the-command-line/)
