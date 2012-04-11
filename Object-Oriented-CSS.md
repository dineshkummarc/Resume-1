# Object-Oriented CSS

Below is how I am currently structuring my CSS to be more object-oriented (OOCSS) with a little assistence from Sass:

* Base
* Variables
* Mixins (*careful and limited usage*)
* Extensions (*careful and limited usage*)
* Layout
* Modules
* State
* Theme

Below we discuss the last four items in more detail… 

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

.m-posab {
    position: absolute;
}

.m-alignleft {
	float: left;
}

.m-alignright {
	float: right;
}

.m-media {}
.m-box {}
.m-strapline {}
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