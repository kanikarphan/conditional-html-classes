Conditional HTML Classes
=====================

A series of IE conditional comments apply the relevant IE-specific classes to the 'html' tag. This provides one method of specifying CSS fixes for specific legacy versions of IE.

When using the conditional classes technique, applying classes to the 'html' element has several benefits:
* Less HTTP requests (calling 1 stylesheet rather than 2 or 3).
* It keeps your CSS rule in one place.
* It can improve the clarity of code in multi-developer teams.
* It avoids the need for an empty comment that also fixes the above issue.
* It still validates as HTML5.

## Here's the magic
```
<!--[if (IE 7)&!(IEMobile)]><html class="no-js ie ie7 lt-ie8 lt-ie9" lang="en"><![endif]-->
<!--[if (IE 8)&!(IEMobile)]><html class="no-js ie ie8 lt-ie9" lang="en"><![endif]-->
<!--[if (IE 9)&!(IEMobile)]><html class="no-js ie ie9" lang="en"><![endif]-->
```

## How to Use it
With the above markup in place we can do stuff like this in within the core stylesheet
```
h1 { color: pink } 
.ie7 h1 { color: black }
.ie9 h1 { color: blue }
```

## Each class stands for...
```
ie - All version of internet explorer
ie7 - internet explorer version 7
lt-ie8 - internet explorer version less than 8
ie8 - internet explorer version 8
lt-ie9 - internet explorer version less than 9
ie9 - internet explorer version 9
```

## What about ie10?
Microsoft has decided to <a href="http://www.sitepoint.com/microsoft-drop-ie10-conditional-comments/" target="_blank">remove conditional comments from Internet Explorer 10</a>.