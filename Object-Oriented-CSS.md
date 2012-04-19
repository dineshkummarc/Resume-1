# Object-Oriented CSS

Below is how I am currently structuring my CSS to be more object-oriented (with a little assistence from Sass):

* Base
* Helpers
* Variables (see my [Guide to Sass](https://github.com/Integralist/Blog-Posts/blob/master/Guide-to-using-SASS.md))
* Mixins (*careful and limited usage* - see my [Guide to Sass](https://github.com/Integralist/Blog-Posts/blob/master/Guide-to-using-SASS.md))
* Extensions (*careful and limited usage* - see my [Guide to Sass](https://github.com/Integralist/Blog-Posts/blob/master/Guide-to-using-SASS.md))
* Layout
* Modules
* State
* Theme

##Base

My base file is normally just called `build.css`. 

Within that file I'll `@import` all the stylesheets I need. Normally you wouldn't use `@import` statements because they're bad for page loading performance (they block the loading of other stylesheets and elements on the page - see [Steve Souders](http://www.stevesouders.com/blog/2009/04/09/dont-use-import/) post on this from 2009 for more information).

If you're using Google's `modpagespeed` Apache module on your server then you no longer have to worry about using `@import` because the latest version now flatterns the imports ([See the issue I submitted which resulted in a bug being discovered and fixed](http://code.google.com/p/modpagespeed/issues/detail?id=398&can=1&q=%40import&sort=-status&colspec=ID%20Type%20Status%20Priority%20Milestone%20Modified%20Owner%20Summary)). 

Alternatively if you're using a pre-processor such as [Sass](http://sass-lang.com/) then you'll be able to import stylesheets and leave it up to Sass to automatically flattern them for you (which is what I'm doing in my projects).

```
// This is our "base"
@import "normalise";

// Miscellaneous helper classes
@import "helpers";

// Project specific
@import "variables";
@import "layout";
@import "modules";
@import "state";
@import "theme";
```
Below we'll discuss the last four items (layout, modules, state and theme) in more detail… 

##Helpers
Modules are re-usable design 'patterns' (such as the ['media object'](http://www.stubbornella.org/content/2010/06/25/the-media-object-saves-hundreds-of-lines-of-code/)) where as these helpers (although like modules) are different in that they are re-usable layout utilities.

```
// ClearFix - http://www.nicolasgallagher.com/micro-clearfix-hack/
.h-clearfix {
	zoom:1; // IE6/7
}

.h-clearfix:before,
.h-clearfix:after {
	content: "";
	display: table;
}

.h-clearfix:after {
	clear: both;
}

// Hoz Block (Horizontal) - http://csswizardry.com/2011/09/the-nav-abstraction/
.h-hoz {
	list-style: none;
	padding-left: 0;
}

.h-hoz,
.h-hoz dd {
	margin-left: 0;
}

.h-hoz li,
.h-hoz dt,
.h-hoz dd {
	display: inline;
}

.h-hoz a {
	display: inline-block;
}

// Image Replacement - http://www.zeldman.com/2012/03/01/replacing-the-9999px-hack-new-image-replacement/
.h-hidden {
	text-indent: 100%;
	white-space: nowrap;
	overflow: hidden;
}

// Container Block
.h-container {
	display: block;
	margin-left: auto;
	margin-right: auto;
	padding: 0 10px;
	max-width: 940px;
	width: 90%;
}
```

##Layout
Divide the page into sections. Layouts hold one or more modules together.

**Pattern**

```
.l-<layout-type>
```

**Examples**

```
.l-container
.l-nav
.l-basket
.l-footer
```

##Modules
These are the reusable, modular parts of our design.

**Pattern**

```
.m-<module-type>
```

**Examples**

```
.m-btn {
    @extend .transition;
	
    background-color: $brand-A-main;
    color: $brand-A-sub;
    font-family: Helvetica, Arial, sans-serif;
    font-size: 85%;
}

// Media Block - http://www.stubbornella.org/content/2010/06/25/the-media-object-saves-hundreds-of-lines-of-code/
.m-media {
	display: block;
}

.m-media-img {
	float: left;
	margin-right: 10px;
}

.m-media-body {
	overflow: hidden;
	margin-bottom: 0;
}
```

##State
The ways to describe how our modules or layouts will look when in a particular state. 
Is it hidden or expanded? Is it active or inactive? 
They are about describing how a module or layout looks on screens that are smaller or bigger. 
They are also about describing how a module might look in different views like the home page or the inside page.

**Pattern**

```
.is-<state-type>
```

**Examples**

```
.is-hidden
.is-collapsed
.is-expanded
```

##Theme
These are similar to state rules in that they describe how modules or layouts might look. 
Most sites don’t require a layer of theming but it is good to be aware of it.

**Pattern**

```
.t-<theme-type>
```

**Examples**

Following classes would represent seasonal theme over-rides: 

```
.t-autumn
.t-spring
.t-summer
.t-winter
```

## JavaScript Components
Used to provide JS-only hooks for a component. Can be used to provide a JS-enhanced UI or to abstract other JS behaviours. These ideally should be set using the `id` HTML attribute as it's more efficient for the JavaScript engine to access these elements using the host method `getElementById`.

**Pattern**

```
js-action-name
```

**Examples**

```
js-submit
js-action-save
js-ui-collapsible
js-ui-dropdown
js-ui-dropdown--control
js-ui-dropdown--menu
js-ui-carousel
```