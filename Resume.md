#Resume

This document is quite long, but please do take the time to have a good read through each section, as within I have included additional comments regarding techniques and other points of interest that I've come across while working with different technologies, devices and browsers (especially working within new areas of HTML5 and mobile development).

I feel these are important experiences worth including.

Of course if you have any questions then please just let me know.

Many thanks.  
Mark McDonnell 

---

* Bio
* Core skills
* Other skills
* Experience
* Examples
* Software
* Inspiration
* Personal traits
* Interests

##Bio

My name is Mark McDonnell, I'm 29 and I work for a creative agency in the South-East of England (I've worked with this agency for just over 11yrs now - as you can see I'm a loyal worker).

I can be found online at the following locations:

* [integralist.co.uk](http://www.integralist.co.uk/)  
* [twitter.com/integralist](http://www.twitter.com/integralist)  
* [github.com/integralist](https://github.com/integralist)

The new HTML5 capabilities and mobile solutions available today really excite me. Learning and using new technology is what I'm passionate about and so I'm keen to move forward into these areas as much as possible. The idea of building applications that work across multiple devices is both fun and very refreshing to me.

But most importantly, I just love to learn.

##Core skills

Below is a short list of technologies I work with (on a daily basis) followed with a more detailed break down of each… 

| Core       | Secondary              |
| -----------| ---------------------- |
| HTML/5     | Regular Expressions    |
| CSS/3      | Git Version Control    |
| JavaScript | Command Line Interface |


###HTML

The bread and butter of any front-end developer. My approach to new projects is to:

* print out the designs
* mark-up the different components in pen (I also like to sketch out the page in a notepad)
* think about how I'm going to apply styles (using [OOCSS](https://github.com/stubbornella/oocss/wiki) patterns)

This process helps me understand the elements that make up the page and gives me a solid plan of action before writing a single line of code.

**Semantic Elements**

I make sure to use semantic elements that suit the content, rather than selecting elements because they're easier to style (yes, I've seen that happen). It's important to understand why I've chosen to use a certain element, otherwise the page will just end up being filled with `<div>`'s and `<p>`'s but no real semantic structure.

**HTML5**

I also use new HTML5 elements wherever possible with the help of [HTML5shiv](https://github.com/aFarkas/html5shiv) for IE < 9 compatibility.

My first proper introduction to HTML5 was via Mark Pilgrim's "Dive into HTML5" (which was then released by O'Reilly as "HTML5 Up and Running"). Following that I started reading [Introducing HTML5](http://introducinghtml5.com/) by Remy Sharp & Bruce Lawson which covers topics such as the new semantic elements, form elements, video/audio, storage facilities, canvas, websockets, cache manifest, geolocation - a lot of useful information.

**Note**: I discovered while working with the `<audio>` element that in some browsers they will refuse to hide these new media elements (`<video>` included) using traditional methods such as `display:none` or positioning offscreen. I consulted with the online community (e.g. twitter/github) and it turned out that I had to incorporate a CSS3 'transform' to trick the browser into displaying the audio element offscreen.

**Style Guide**

I've also written up a [HTML Style Guide](https://github.com/Integralist/Style-Guides/blob/master/HTML%20Style%20Guide.md) which might be of interest in how I currently format my code.

---

###CSS

**Object-Oriented CSS**

A few months ago I started looking into ways to make my CSS more flexible and scalable. Via Nicole Sullivan and [Jonathan Snook](http://smacss.com/) I discovered the principles of object-oriented CSS (OOCSS).

In short, OOCSS is the separation of layout/structure and skin/themes - taking an object that has repeatable style and turning it into a reusable module.

With OOCSS my projects have become simpler, more scalable and much easier to extend compared to any other style of CSS I've tried in the past.

I'm still working on refining how I use OOCSS but for more information on how I'm *currently* structuring my CSS please see my post about [Object-Oriented CSS](https://github.com/Integralist/Resume/blob/master/Object-Oriented-CSS.md) on GitHub

**Responsive Design**

I like to use a 'mobile first' responsive design approach to my website builds now. This means loading stylesheets for mobile devices first and then using Media Queries to load additional stylesheets for larger screens/devices. This means assets specifically for larger devices don't get downloaded onto smaller devices which would struggle to handle them. 

I also use techniques such as:

* Set `font-size` on `body` to `100%` as this translates to `16px` on most browsers.
* Once `font-size` is set we can use the calculation: 'target / context' to determine the dimensions of other fonts or elements (in either `em` or `%`). This lets me convert precision px designs into more fluid/scalable designs.
* I also set a `max-width` onto images so they scale appropriately. 

For example, if you have a design with a width of `960px` (and assuming the `font-size` on the `body` has been set to `100%`) then we can make this fluid by running the following calculation:

`960px / 16px = 60em` so we set a `max-width` onto the top level element to be `60em` wide.

**Remember**: when setting percentages you'll need to move the decimal point over two places to the right. So for example if your calculation results in `0.7085` then the percentage value would be `70.85%`.

**CSS3**

I like using new CSS3 features wherever possible for more capable browsers. Due to the type of designs (and clients) our agency works with we don't get many chances to do anything too '*funky*', so mostly I use transitions for colour/display changes which gives pages a subtle but slick enhancement. But every now and then we'll be able to throw in a quick animation or transform to give the page an extra edge (**Warning**: on Android devices lower than version 4.0 it would appear that animations are supported but they really only support animations if you're working with a single property! otherwise more than one property will cause the element to disappear).

Tools like [Modernizr](http://modernizr.com/) help provide fallback solutions but there are so many new useful CSS3 features available now that I look forward to the day/project whereby I can utilise these more without having to worry about older browser support.

**Pre-Processors**

In the past I was very much against the use of pre-processors such as Less/Sass (even more so since discovering OOCSS) because it seemed that developers were using them in a fashion similar to jQuery: where it's a magic black box that just does everything for them and they have no consideration for the resulting stylesheet efficiency. But as long as you know what problems can occur when using a pre-processor (and try to avoid them) then the benefits that it brings can outweigh the negatives and make you much more productive as a result. 

I've written a [blog post about Sass](https://github.com/Integralist/Blog-Posts/blob/master/Guide-to-using-SASS.md) which goes into more detail as to how it can be used.

**CSS Sprites**

I use CSS image sprites wherever possible as it's more efficient to make one HTTP request for a single large image than multiple (easily twenty or more) HTTP requests for very small images (like graphical buttons, icons etc). 

I know some people find them to be a hassle, but I've never really encountered any issues with using them. Sometimes it's annoying having to make the overall canvas size of the sprite larger just to accommodate an image with awkward dimensions, but I hardly see that as a major concern (the extra white space is negligible).

**Performance Considerations**

There is still a lot to be considered when writing scalable CSS (especially when your project is targeting a mobile device - where bytes and connection speed count). For example, typically (in any project) you'll want to reduce HTTP requests, so you'll combine your CSS into a single file (this is where Sass can be really useful as it helps keep files modular while allowing you to build the result into a single stylesheet) but you don't want to just load all your CSS into a single stylesheet as the majority of it wont be relevant for the current page, so you still need to think about your application and consider having different stylesheet builds for the different areas (again this is something Sass can make a lot easier**)

***But if you weren't using Sass then instead this could be achieved by using a custom build script (compiled for example via Apache Ant). Or you could develop a server-side build script that dynamically takes the stylesheets in the page and concatenates/caches them for you (our server does this via the [Google modpagespeed Apache module](http://code.google.com/p/modpagespeed/) - I had written [a basic concatenation script in PHP](http://integralist.co.uk/Mini-Com/) years ago which I had been meaning to re-write to be more flexible but I might try re-writing it in Ruby now - see 'Other skills' for more information as to why).*

**Style Guide**

I've also written up a [CSS Style Guide](https://github.com/Integralist/Style-Guides/blob/master/CSS%20Style%20Guide.md) which might be of interest in how I currently format my code.

---

###JavaScript

I love JavaScript.

If there is one subject I enjoy reading about the most, it's JavaScript. I have so many books from such amazingly talented authors as: [Stoyan Stefanov](http://shop.oreilly.com/product/9780596806767.do) (who recommended me to Facebook), [Marijn Haverbeke](http://eloquentjavascript.net/), [Dustin Diaz](http://www.apress.com/programming/javascript/9781590599082), [Nicholas C. Zakas](http://shop.oreilly.com/product/9780596802806.do), [Alex MacCaw](http://shop.oreilly.com/product/0636920018421.do), [David Flanagan](http://shop.oreilly.com/product/9780596805531.do)… the list goes on.

**Design Patterns for code reuse**

When it comes to code reuse in JavaScript I prefer to stay away from inheritance and instead use composition. Take a look at two ways I do this using [*method*.call and mixins](https://gist.github.com/1391785).

**Modular Code**

Up until around August 2011, to keep my code clean and modular, I was using the script loader [LABjs](http://labjs.com/) along side my own tiny bootstrap library which would lazy-load any scripts required for the current page. I would have a single namespace and in each script lazy-loaded I would attach the function to the namespace. [See here for an example](https://gist.github.com/2385187).

But now I use [AMD](https://github.com/amdjs/amdjs-api/wiki/AMD) (Asynchronous Module Definition) for writing more modular code. The two most popular AMD loaders available are [RequireJs](http://requirejs.org) and [Curl](https://github.com/cujojs/curl), and although Curl is (supposedly) faster and has a more modern interface (uses a Promises/Deferred style API) I prefer using RequireJs as it's much cleaner and the build script is very flexible and easy to use. 

[Addy Osmani](https://twitter.com/#!/addyosmani) (now at Google) asked me if he could add [my post on AMD/RequireJs](https://github.com/Integralist/Blog-Posts/blob/master/Beginners-guide-to-AMD-and-RequireJs.md) to the new jQuery learning website which I was very pleased about and was happy to contribute.

**Performance and Efficiency**

Whenever writing JavaScript for a large scale application it's important to remember about performance. Normally it's a good to have an idea while you're building your application to write code in such a way that you know you'll be preventing bottlenecks later in the applications life, but this isn't always possible or even the best way to go as some of your performance improvements could be in all the wrong places or could just end up as 'micro optimisations'.

The best way to check performance of your application is to use some form of script profiler that will analyse your code and feed back information on its call stack and how often certain functions are executed. There are a few different profilers available such as:

* dynaTrace AJAX Edition
* Firebug Profiler
* WebKit Developer Tools: Profile

Good learning material for JavaScript performance is the [JavaScript Performance Rocks!](http://javascriptrocks.com/performance/) collection by Thomas Fuchs. I highly recommend it. But also "High Performance Websites" and "Even Faster Websites" by Steve Souders, and lastly "High Performance JavaScript" by Nicholas C. Zakas.

**Frameworks**

My principles are to 'roll my own' wherever possible. I'm not a huge fan of using large frameworks such as jQuery, and I also understand and appreciate the concerns that are raised when people talk about using lots of 'micro-libraries'.

The core things I need to do most of the time is animations (which in itself isn't too difficult, it's just about getting the 'easing' equations right - which there are many available already) and doing XHR based interactions ([here is my ajax script which is heavily based on jQuery](https://github.com/Integralist/Project-Template-Files/blob/master/Assets/Scripts/Utils/XHR/ajax.js)).

For animations I like to use the [Morpheus](https://github.com/ded/morpheus) library as it's very flexible and highly optimised.

And for asynchronous interactions I like using [when.js](https://github.com/cujojs/when) which is a great Promises/Deferred library which can be used both client-side and server-side within NodeJs.

**Resources**

Two useful resources for new ECMAScript features is [Juriy Zaytsev](http://perfectionkills.com/)'s compatibility tables:

* [ES5](http://kangax.github.com/es5-compat-table/)
* [ES6](http://kangax.github.com/es5-compat-table/es6/)

**Style Guide**

I've also written up a [JavaScript Style Guide](https://github.com/Integralist/Style-Guides/blob/master/JavaScript%20Style%20Guide.md) which might be of interest in how I currently format my code.


**Blog Posts**

Finally, here are a couple of quick posts I have written about JavaScript:

* [Host Methods vs Native Methods](https://github.com/Integralist/Blog-Posts/blob/master/Host-Methods-vs-Native-Methods.md)
* [JavaScript Inheritance](https://github.com/Integralist/Blog-Posts/blob/master/JavaScript-Inheritance.md)

---

###Regular Expressions

I really enjoy writing regular expressions. I seem to use them as much for general operating system file/text based requirements as I do in web development. 

When used for the web the key is to be as efficient with your regexes as possible and to avoid issues such as [runaway back-tracking](http://www.regular-expressions.info/catastrophic.html) which can be devastating to the performance of the regex engine. I use [RegexBuddy](http://www.regexbuddy.com/) for analysing back-tracking performance (just a tragedy it's not available for Mac OSX - as I have to fire up a Windows VM whenever I need to use it). Regexes for the web are best written to be small and concise (e.g. two small regexes are better than one overly complicated monolithic one).

The following is a post about [using JavaScript with Regular Expressions to open external links in a popup window](https://github.com/Integralist/Blog-Posts/blob/master/Regex-Popup-Window.md) - the regex itself could be improved but for the purpose of the article it was fine.

Also, the regex legend that is [Steven Levithan](http://blog.stevenlevithan.com/) released his regex syntax highlighter after [prompted by my interest in it](http://blog.stevenlevithan.com/archives/regex-syntax-highlighter) - something I geeked out over obviously :-)

---

###Git Version Control

I wrote a post about [how to use Git and GitHub](https://github.com/Integralist/Blog-Posts/blob/master/How-to-use-Git-and-GitHub.md) which [Paul Irish](http://twitter.com/paul_irish) from the Google Developer team [shared with the community](https://github.com/h5bp/lazyweb-requests/issues/14#issuecomment-701244) (as he was looking for this exact type of article as part of his lazy web requests project).

My current employer uses GitHub to host both private and public repos. I'm still a bit green when it comes to using things like sub modules but I'm more than comfortable using Git for version tracking my files locally and doing all the standard remote push/pull/merge commands. 

We're still trying to figure the best work-flow between a team of developers (as there appears to be many ways to '*skin a cat*'). Currently we use GitHub to host our private repositories: we then set-up a `dev` branch which we `pull` to our remote server where we test that branch before merging it back into the `master` branch (the `master` branch should always be deployable!)

---

###Command Line Interface

I use the Terminal on the Mac (which is a [Bash](http://en.wikipedia.org/wiki/Bash_%28Unix_shell%29) shell). 

I use the CLI for CSS linting (using [CSSLint](http://csslint.net/)), JavaScript linting (using [JsHint](http://www.jshint.com/)) as well as connecting to our remote servers via SSH and carrying out basic tweaks and changes (but nothing major as I'm not really a server engineer). 

I've written a quick blog post on using [NodeJs as a build tool](https://github.com/Integralist/Blog-Posts/blob/master/NodeJs-as-a-tool.md) which explains a little bit on how I use the CLI for things like generating documentation as well as linting CSS/Js.

##Other skills

Below is a short list of other technologies I have worked with (or do work with) followed by a more detailed break down of each…

|              |                                                                                   |
| ------------ | --------------------------------------------------------------------------------- |
| Mobile       | I'm getting the opportunity to work with on a more regular basis now              |
| TDD          | I use but not as much as I'd like to in my current role (due to time constraints) |
| PHP          | Have used lots in the past, but haven't used it fully in a good few years         |
| Ruby         | I've only just started getting into                                               |
| ActionScript | I used a fair bit in the past but hate with a passion                             |

###Mobile

There are a few different mobile options available:

* Mobile first
* Mobile friendly website
* Mobile web app

**Mobile first**

Mobile first is the preferred solution as it means you only serve stylesheet content for the relevant device dimensions. This means not loading a desktop size stylesheet for a mobile device which means extra bandwidth required for the mobile device downloading content it will never use.

The way to do this is to have a 'base' stylesheet for mobile devices and to then use Media Queries to load additional stylesheets for each screen dimension required which overwrite those base rules. Then for browsers such as Internet Explorer that do not understand Media Queries you would wrap the 'desktop' stylesheet in a conditional comment (e.g. `<!--[if lt IE 9]>`) so that for IE browsers they would still get the desktop experience.

See a basic example of this (via my GitHub account) with the project: "[Mobile First, Desktop Second](http://integralist.co.uk/Mobile-First-Desktop-Second/)".

**Mobile friendly website**

This solution is not as good as the 'mobile first' approach but is better than nothing. The idea is that once your website has been developed you then use Media Queries to load additional stylesheets to overwrite certain rules so when your website is viewed on a smaller screen the different page elements are either shifted into a more linear layout, resized or just hidden altogether. I use this approach on my website [www.integralist.co.uk](http://www.integralist.co.uk/)

**Mobile web app**

The last solution is to make your website look and function more like a 'native' app, but only for mobile based devices. So if the user is visiting your site on their desktop computer then they'll notice no difference. But if they are visiting using a mobile or tablet device then they'll be automatically redirected to your 'web app' which is designed specifically to look more like a 'native' app and should also have more 'app' like functionality compared to your normal website. This solution isn't appropriate for all clients because it depends on their product and what the user can do when visiting their site.

**Difficulties with each of these mobile 'solution'**

For 'mobile first' the main issue is how do you handle loading images? This sounds simple enough but in practice there currently doesn't appear to be a perfect solution. A couple of work arounds could be to: 

* load the full size image and using `max-width:100%` to help the images scale to the device dimensions (but then you're loading very large images on a small bandwidth device).
* use a server-side script to specify the full sized image be set in a HTML5 `data-attribute` and then you can use JavaScript to load the relevant image depending on the device dimensions (but then you're relying on JavaScript to be available which might not be the case on every device).

For 'mobile friendly websites' the issue is that again a small bandwidth device is having to download the full site assets (images/stylesheets/javascript).

For 'mobile web apps' there is the tricky process of determining: when should the user be directed to the website or the web app? Again there currently are no perfect solutions. There are a few different techniques that attempt to work around this issue and the one I prefer (the lesser of all evils) involves using JavaScript to determine screen dimensions and then redirecting the user to the web app where the server-side sets a cookie to remember the user. The flaws with this solution is that JavaScript and cookies are required. But the alternatives require browser sniffing and/or checking the browser's user-agent against a database of devices (which is a fragile '*solution*' to say the least).

Each of these issues have a multitude of potential work arounds, but which one to use depends on the project requirements and timescales.

**Current work flow**

The agency I work for currently doesn't take a 'mobile first' approach unless we've already had an agreement from the client to do so (usually clients prefer not to take this route as it means extra design and programming time/costs - so they'll normally decide to take the 'mobile friendly' approach).

Working for mobile has been made easier through my research and use of:

* OOCSS (e.g. [Scalable and Modular Architecture for CSS](http://smacss.com/book/))
* [Responsive Design](http://www.abookapart.com/products/responsive-web-design)
* [Adobe Shadow](http://www.pcpro.co.uk/blogs/2012/03/20/adobe-shadow-a-free-way-to-test-mobile-sites/)
* [HTML5 Mobile Pro](http://html5mobilepro.com/) (which I've not completed reviewing yet)

---

###TDD (Test-Driven Development)

I like the philosophy behind [TDD](https://en.wikipedia.org/wiki/Test-driven_development) but I mostly end up writing 'unit-testing' code rather than actually doing TDD. This is because I don't have the luxury of time in my current role to spend designing out an API, it's a very fast pace office which requires code to be written and working without delay (which is unfortunately typical of a lot of agencies). But I understand the concepts & the benefits, and very much believe TDD to be a great way to design and build your code.

I've written a blog post about [using the BDD testing framework Jasmine](https://github.com/Integralist/Blog-Posts/blob/master/Beginners-guide-on-how-to-test-your-code-%28using-Jasmine-BDD%29.md) - this was before I found [BusterJs](http://busterjs.org/) which is just an amazing TDD framework that is run via command line where it sets up a localhost and you can attach different browsers as 'slaves' for it to test against (similar to how the jsTestDriver framework worked - which I tried out years ago back when I used MSFT Windows). 

---

###PHP

I used to do a fair bit of PHP a few years ago. I learnt about object-oriented programming and ended up building some basic Content Management Systems. But I haven't written anything other than basic quick PHP scripts for years. See [this basic PHP JavaScript/CSS minification script](http://integralist.co.uk/Mini-Com/) I wrote.

As far as aesthetic are concerned it has to be said that PHP is fugly as hell (but that's just my personal opinion). 

I find the 'HipHop for PHP' (PHP into C++) compiler Facebook has written to be an interesting way to improve performance of the language, but regardless I'm not a huge fan of PHP (as far as writing it is concerned) especially since being introduced to [Ruby](http://www.ruby-lang.org/en/).

---

###Ruby

I started learning Ruby because I wanted to understand the concepts behind CoffeeScript and the new functional features in ES5 (and more so in ES6). I've since written a [blog post about Ruby](https://github.com/Integralist/Blog-Posts/blob/master/Introduction-to-Ruby.md) and my thoughts on it so far.

Although I'm not a server-side developer, I think I've fallen in love with the language and so I'm looking forward to learning more about it (and getting to use it) in the future. At the very least it'll make understanding the CoffeeScript syntax a lot easier!

---

###ActionScript

I used to use the ActionScript 3.0 language quite a bit a few years ago (before HTML5 and JavaScript blew up and Apple had driven a stake through the heart of Flash on mobile).
 
I'm mentioning my use of AS3 simply because every now and then Flash makes a recurrence in my life. For example, in the last web application I worked on we needed to use a 3rd party ActionScript library for recording a user's microphone input. This was so the user could attach audio to their profile as a way to introduce themselves to other users.

Personally I hate writing Flash applications and I hope I never have to deal with it again :-)

##Experience

With my current employer (who I've been with for the last 11yrs) I have worked my way up the ranks from a junior front-end developer (who at the time knew nothing other than how to use Macromedia's DreamWeaver 3!) to head of our Digital Media Department. I'm completely self taught/driven. My interest in programming, technology and the love of learning new things is what has gotten me to where I am today.

**Management & Programming**

For the last (almost) two years I've taken up a management role where I look after a team of three developers (two back-end and one front-end). 

I still write code on a daily basis, but most of the time it's helping the team with any problems they have (specifically the front-end, although having back-end knowledge sometimes allows me to throw a new perspective at a problem which has then helped the team locate the issue and implement an appropriate solution).

I had hoped this role would've given me a chance to write more experimental code and learn new technologies (something I just didn't have time for before), unfortunately management brings both benefits and its own struggles, and so I still do not have the time to play with new things as much as I would like to. 

This role has been a much more enlightening experience than I could have imagined (it's hard to balance how you handle your own work load and also keep a separate team afloat, all without hovering over their shoulders in a panic about whether jobs are getting done in time and to an acceptable standard). Having trust in your team is critical.

---

**My Team**

My team was effectively all juniors who (like me, they have learnt the majority of their skills off their own hard work) have benefited from my direction and experience, so they have been able to improve their own skills much faster than if left on their own.

Our two back-end developers have now written their own light-weight MVC based Content Management System frameworks - which work very nicely - and so I'm very proud of them both, considering they came to me with nothing but procedural/spaghetti code. 

Our front-end developer was much the same - coming to us with basic HTML and CSS skills but (being young and from a generation that has grown up with the web at their finger tips) he had interests in all the right technologies and so it was easier for me to guide him (especially as I'm a front-end developer myself as it made it easier to share specific parts of my knowledge and experience).

---

**Small Company = Hard Work**

Working for a small creative agency is actually very difficult because there is no way to get 'lost in the crowd' which can happen in bigger companies. You also have greater responsibility over a much wider area. In larger companies, a developer is just a developer, a manager is just a manager and their roles don't usually cross over. But when there are less people working for the company, that changes things, and so for the company to succeed every employee needs to take a pro-active interest in what goes on.

---

**My role currently involves**:

* Programming
	* front-end of websites
	* prototyping more unique functionality
* Managing 'Digital Media' Department
	* Delegating work to staff (programmers)
	* Ensuring work is done on time
	* Helping with any questions or issues they have
	* Dealing with clients
	* Looking after invoicing
	* Looking after dedicated web server
		* We use UKFast as our server provider and so their engineers look after the physical running of the server, but I SSH on to the server on a regular basis and check resource usage, error logs, install/update modules (such as the [Google Pagespeed Module](https://developers.google.com/speed/pagespeed/mod)) and things of that nature.
* Project Manager
	* Meeting with clients and understanding requirements
	* Booking in work with different departments (creative, copy writing)
	* Creating schematics/architecture of application
	
---

**Mobile applications**:

With regards to Mobile development, we've developed a couple of web applications using jQuery Mobile (unfortunately these aren't released to the public yet) and although they work very well and the choice to use jQuery Mobile was valid (we had a seriously tight deadline for both + the team were new to mobile development and the client's own requirements were to target as many devices as possible), I'm personally a bit disappointed we didn't have more time to consider other options. 

I would have preferred to have either gone down a 'home grown' route or at least used a much more lightweight solution such as [ZeptoJs](http://zeptojs.com/) (which was designed with mobile in mind) - and that way we could have written our own much slimmer CSS/Js and had cleaner structured HTML (I'm planning on setting aside some time soon to build a test application using ZeptoJs and writing up my findings in a separate blog post).

---

**My last programming project**:
	
My last big *programming* project (which is currently in client testing phase) was a very large scale social network web application which I developed the front-end for (and a majority of the JavaScript interactions). 

I worked along side a freelance back-end PHP developer who handled the JavaScript XHR'ing of data back and forth. But we worked together on solutions for how to handle server load more efficiently. One such item we worked on was how to fake 'push notifications'. To do this we decided that we wouldn't do the traditional 'polling' method (where you have a set interval of when to call the server for information), we would instead track the users mouse movement on a set interval and increase the length of the delay depending on the lack of change in the data sent from the server. 

So for example, when the user moved their mouse we would send a call to the server. We would then set a timer to check the mouse move event in 30 seconds time. If the user moved their mouse again after 30 seconds then we'd again call the server, but additionally we would check if the data from the server had changed at all. If it hadn't changed then we would reset the timer to be longer than 30 seconds before calling the server again.

This particular project has been going on for about two years now - the last year has been working on the web application itself - after spending almost a year on building an initial mock website along with planning documents and drawing up schematics for the front-end as well as the different user management systems required for this application (a very lengthy procedure).

It was this project that made me realise the importance of scalable CSS and what spurred me to investigate OOCSS further and now to have incorporated it into my work flow.

---

**Clients:**

In the past we've worked with the BBC and the Arts Council, local government and currently do lots of work for the [NHS](http://en.wikipedia.org/wiki/National_Health_Service). 

The last project we built for the NHS was a campaign to stop people going to A&E when it wasn't an emergency: [http://www.notalwaysaande.co.uk/](http://www.notalwaysaande.co.uk/). My involvement was primarily to manage the team developing the website but also was to help guide our front-end developer - who was still early in his JavaScript learning - as to how he could build the relevant map functionality required for this project (which was to display a list of custom locations approx two miles from the users location - along with some other interactions with the map - the user would enter their postcode as part of the search criteria and we'd geo-encode it using Google's Map API).

I mention this NHS project as it ties in with the 'upcoming project' I've listed below.

---

**Upcoming project**:

*NHS A&E iPad app*

We were contacted recently on the possibility of taking the A&E campaign website and turning it into an offline application compatible with the iPad.

Next week I will be sitting down and working out how best to implement this, but my initial thoughts were to:

* find out support for [Indexed Database API](http://www.w3.org/TR/IndexedDB/) as it might be needed for certain areas of the site that are dynamically populated by a bespoke CMS.
* look into the Application Cache Manifest so we can take the content offline

…I'm very much looking forward to this project and having the chance to work out how it should be put together.

##Examples

Because of the management role I've been in for the past (almost…) 2yrs, I do not have a huge back log of what you would call 'full blown' examples (e.g. websites/applications that I've worked a large portion on).

My last big programming project was a social network web application, but as that is not yet public I'm unable to provide much more information (other than what I've detailed above within the "Experience" section) as to what that project entailed, or more importantly: code examples. 

Below I have listed items I think might be of interest. Please be aware that some of these examples were put together quite quickly (either me testing some new technology or as a quick prototype for work):

Please see the README files for each example for more information…

* [HTML5 Canvas Sliding Image Game](http://integralist.co.uk/HTML5-Image-Slider-Game/)
* [Card Generator using HTML5 Canvas](https://gist.github.com/1973726) (Gist)
* [XHR 2.0 Multiple File Upload (with PHP)](http://integralist.co.uk/XHR2-Multiple-File-Upload--with-PHP-/)
    * [+ resize/recolour of images using HTML5 Canvas](https://github.com/Integralist/XHR2-Multiple-File-Upload--with-PHP-/tree/canvas)
* [Mobile First, Desktop Second](http://integralist.co.uk/Mobile-First-Desktop-Second/)
* [Google Maps with Geolocation + HTML5 Audio + Google Places](https://gist.github.com/1710256) (Gist)
* [HTML5 History API](http://integralist.co.uk/HTML5-History-API/)
* [MVC Start-up Kit](http://www.integralist.co.uk/MVC-Start-up-Kit) (jQuery Version)
    * [library agnostic version](https://github.com/Integralist/MVC-Start-up-Kit/tree/library_agnostic)
* [Robust DOM ready function](http://integralist.co.uk/DOMready/)
* [Project Template Files](http://integralist.co.uk/Project-Template-Files/)
* [integralist.co.uk](https://github.com/Integralist/integralist.github.com) (Utilises Media Queries for resizing content depending on device)
* [XHRl - AJAX based Script Loader](http://integralist.co.uk/XHRl/)
* [Tabbed Interface](http://integralist.co.uk/Tabbed-Interface/)

##Software

My software toolkit:

* iMac 27" with OSX Lion (at home I use a MacBook Pro)
* Browser of choice: (at work…) Latest Firefox (at home…) Firefox Aurora
    * Used to be Chrome but I much prefer Firebug than WebKit Dev Tools (amongst other things)
* [Chocolat](http://www.chocolatapp.com/) (for programming - not really an IDE - just small/quick with some nice features built-in)
* [Mamp Pro](http://www.mamp.info/) (Local Web Server)
* [Parallels Desktop](http://www.parallels.com/uk/products/desktop/) (for IE testing using [IECollection](http://utilu.com/IECollection/) which is a more accurate representation of IE rendering than IE's `DocumentMode` settings)
* Adobe Shadow (new tool for testing applications on multiple devices at once)
* [Mou](http://mouapp.com/) (Markdown editor - which I use for writing blog posts)
* [jsperf](http://jsperf.com/) (Any time I need to confirm my suspicions on Js performance)
* [jsfiddle](http://jsfiddle.net/) (Great for a quick front-end test of code)
* [Transmit](http://panic.com/transmit/) (FTP)
* Adobe Illustrator/Fireworks (Design)
* [Domain Brain](http://domainbrainapp.com/) (Domain/Hosting management)
* [Sparrow](http://sparrowmailapp.com/) (Email)
* iCal (managing projects and deadlines)
* [ImageOptim](http://imageoptim.com/) (image reduction/optimisation)
* [RegexBuddy](http://www.regexbuddy.com/) (Regular Expressions)
* Google Pagespeed Module (Web Server Optimisations)

##Inspiration

There are quite a few places I get inspiration from:

* Twitter  
	*A few people who share great information*:
	* [@jdalton](http://twitter.com/jdalton)
	* [@kangax](http://twitter.com/kangax)
	* [@mathias](http://twitter.com/mathias)
	* [@kitcambridge](http://twitter.com/kitcambridge)
	* [@angusTweets](http://twitter.com/angusTweets)
	* [@WebReflection](http://twitter.com/WebReflection)
	* [@thomasfuchs](http://twitter.com/thomasfuchs)
* GitHub
* Newsletters
	* Design Festival Newsletter
	* RubySource Newsletter
	* BuildMobile Newsletter
	* PHPMaster Newsletter
	* SitePoint Newsletter 
	* Js/CSS/Dart Weekly
	* Web Designer Depot
* HTML5 boilerplate  
(initially just the `.htaccess` file I found useful - we incorporated quite a few of the tweaks on our own remote server - but I'm going to be taking a look through their build script (when I get the chance) to see if there is anything I can take from it that will help make me more productive)

##Personal traits

* Loyal
* Hard Working
* Patient
* Humble

##Interests

I love to learn, my main two interests are programming and [Integral Theory](https://en.wikipedia.org/wiki/Integral_Theory).

Otherwise in any spare time I happen to get I'll be:

* Doing/watching martial arts
* Reading
* Listening to music  
(I'm a bit odd in that I love all music genres: metal, house/dance, classical, acoustic, pop - the list goes on…)