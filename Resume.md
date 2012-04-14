#Resume

* Bio
* Core skills
* Other skills
* Experience/Examples
* Software
* Inspiration
* Personal traits
* Interests

##Bio

My name is Mark McDonnell, I'm 29 and I work for a creative agency in the South-East of England (for just over 11yrs now - as you can see I'm a loyal worker).

I can be found online at the following locations:

* [integralist.co.uk](http://www.integralist.co.uk/)  
* [twitter.com/integralist](http://www.twitter.com/integralist)  
* [github.com/integralist](https://github.com/integralist)

I love to learn.

##Core skills

Below is a short list of stuff I work with on a daily basis followed with a more detailed break down of each… 

| Core       | Secondary              |
| -----------| ---------------------- |
| HTML       | Regular Expressions    |
| CSS        | Git Version Control    |
| JavaScript | Command Line Interface |

###HTML

The bread and butter of any front-end developer. My approach for any new project is to print out the designs and mark-up the different components with pen (I also like to sketch out the page in a notepad) as this helps me understand the elements that make up the page. This way I know how I'm going to proceed.

I use semantic elements that suit the content, rather than using an element just because it's easier to style. It's important to know why I'm using a certain element otherwise the page will just be filled with `<ul>`'s and `<div>`'s and have no real structure.

I use new HTML5 elements wherever possible with [HTML5shiv](https://github.com/aFarkas/html5shiv).

###CSS

A few months ago I started taking a serious look at scalable CSS and have begun using principles taken from a variety of different areas which accumulated in more object-oriented CSS (OOCSS). 

I just wish I had started utilising OOCSS sooner (it was half way through working on a social networking web application which would have been made ten times easier/simpler and more extendable with OOCSS). For more information on how I'm currently structuring my CSS please see my post about [Object-Oriented CSS](https://github.com/Integralist/Resume/blob/master/Object-Oriented-CSS.md) on GitHub

I've also been very much against pre-processors in the past (even more so since discovering OOCSS). But I do understand and appreciate the benefits of pre-processors such as Less and Sass and the benefits that they bring. I've written a [blog post about Sass](https://github.com/Integralist/Blog-Posts/blob/master/Guide-to-using-SASS.md) which goes into more detail how it can be used.

There is still a lot to be considered when writing scalable CSS (especially when your project is targeting a mobile device where bytes and connection speed count). For example typically (in any project) you'll want to reduce HTTP requests, so you'll combine your CSS into a single file (this is where Sass can be really useful as it helps keep files modular while allowing you to build the result into a single stylesheet) but you don't want to just load all your CSS into a single stylesheet as majority of it wont be relevant for the current page, so you still need to potentially generate unique stylesheets for different areas of your application.

###JavaScript

I love JavaScript.

I use AMD (Asynchronous Module Definition) for writing more modular code. There are two popular AMD loaders available: RequireJs and Curl, and although Curl is (supposedly) faster and has a more modern interface (uses a Promises/Deferred API) I prefer using RequireJs as it's much cleaner and the build script is very flexible. [Addy Osmani](https://twitter.com/#!/addyosmani) (now at Google) asked me if he could add [my post on AMD/RequireJs](https://github.com/Integralist/Blog-Posts/blob/master/Beginners-guide-to-AMD-and-RequireJs.md) to the new jQuery learning website which I was happy about.

You can see an example of how I use RequireJs and write my JavaScript code from my [Project Template Files](https://github.com/Integralist/Project-Template-Files) repo (obviously I don't use all of it, I strip out any scripts, tests etc that aren't needed for the project - have a look at the README file for more information). From this project you'll notice I have a lot of [modules](https://github.com/Integralist/Project-Template-Files/tree/master/Assets/Scripts/Utils).

For asynchronous interactions I like using [when.js](https://github.com/cujojs/when) which is a great Promises/Deferred library which can be used both client-side and server-side within NodeJs. 

###Regular Expressions

I really enjoy writing regular expressions. I seem to use them as much for general operating system file/text based requirements as I do in web development. 

When used for the web the key to efficient regexes is to avoid runaway back-tracking which can be devasting to the regex engine. I use [RegexBuddy](http://www.regexbuddy.com/) for analysing back-tracking performance (just a tragedy it's not available for Mac OSX - as I have to fire up a Windows VM whenever I need to use it). Regexes for the web are best written to be small and concise (e.g. two small regexes are better than one overly complicated monolithic one)

###Git Version Control

My current employer uses GitHub to host both private and public repos. I'm still a bit green when it comes to using things like sub modules but I'm more than comfortable using Git for version tracking and doing all the standard push/pull/merge commands. We're still trying to figure the best work-flow between a team of developers and using a remote server as a way to push a `dev` branch so we can test merges and then use that as our test bed before merging into the `master` (which should always be deployable!)

###Command Line Interface

I use the Terminal on the Mac (Bash based commands). I use the CLI for CSS linting (using CSSLint), JavaScript linting (using jsHint) as well as basic connecting to our remote servers via SSH. 

I've written a quick blog post on using [NodeJs as a build tool](https://github.com/Integralist/Blog-Posts/blob/master/NodeJs-as-a-tool.md)

##Other skills

|      |
| ---- |
| TDD  |
| PHP  |
| Ruby |

The following skills I:

* Use but not as much as I'd like to in my current role due to time constraints
* Have used lots in the past but haven't used it in a few years
* I've only just started getting into.

###TDD (Test-Driven Development)

Most of the time I end up 'unit-testing' code rather than actually doing TDD. Because I don't have the luxury of time in my current role I'm unable to build build an API in a truly TDD way. But I understand the concepts and the benefits and very much belief TDD to be a great way to design and build your code.

###PHP

I used to do a fair bit of PHP a few years ago. I learnt about object-oriented programming and ended up building some basic Content Management Systems. But I haven't written anything other than basic quick PHP scripts for years. See [this super basic PHP JavaScript/CSS minification script](https://github.com/Integralist/Mini-Com) I wrote.

As far as aesthetic are concerned it has to be said that PHP is fugly as hell (that's just my personal opinion). 

###Ruby

I started learning Ruby because I wanted to understand the concepts behind CoffeeScript and the new functional features in ES5 (and more so in ES6). I've written a [blog post about Ruby](https://github.com/Integralist/Blog-Posts/blob/master/Introduction-to-Ruby.md) about my findings. Although I'm not a server-side developer, I've fallen in love with the language. Looking forward to learning more  about it (and getting to use it) in the future. At the very least it'll make using CoffeeScript a lot easier!

##Experience/Examples

TBA  
discuss projects I worked on and how I help contribute to them

##Software

My software toolkit:

* Mac OSX Lion
* Panic Coda (IDE)
* Transmit (FTP)
* Mou (Markdown editor)
* Mamp Pro (Local Server)
* Adobe Illustrator/Fireworks (Design)
* Domain Brain (Domain/Hosting management)
* Sparrow (Email)
* ImageOptim (image reduction/optimisation)
* RegexBuddy (Regular Expressions)
* Google Pagespeed Module

##Inspiration

TBA  
mention twitter followers and why (jsperf / jsfiddle / github)
newsletters from sitepoint and newsletters like js/css/dart weekly
html5 boilerplate - apache .htaccess file as we were able to incorporate it into our own dedicated server

##Personal traits

TBA  
loyal, hard working, interested in the success of the company

##Interests

TBA  
programming & code / reading / music / martial arts