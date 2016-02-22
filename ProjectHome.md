# jQuery Content Panel Switcher #
**Written By Cheyne Wallace** - http://cheynewallace.com

### <a href='http://cheynewallace.com/demo/jcps/single_demo.html'>Single Panel Demo</a> | <a href='http://cheynewallace.com/demo/jcps/multiple_demo.html'>Multiple Panel Demo</a> ###

<img src='http://cheynewallace.com/demo/jcps/images/jcps.png' align='right' />

<a href='https://github.com/cheynewallace/jquery-content-panel-switcher'>FORK THIS PROJECT ON GITHUB HERE</a>

The jQuery Content Panel Switcher is a simple, very lightweight jQuery plugin that allows smooth transitioning of content in and out of panels located anywhere on the page. You can have single or multiple content switching panels on a single page
Content panels can be either span or div elements, and the buttons used to switch the content can be just about anything, so long as they have the right clases assigned.

Setup is very simple, just create your content, create the panel you wish to switch the content in and out of, create your buttons then assign the appropriate classes and ID's.
Unlike tabbed or folding style content swicthers, the panels and swicther buttons can be located anywhere on the page, any size or shape.
There are two types of transition effects you can pick from, a fader and a slider.

<h2>Extremely Lightweight</h2>
The jQuery Content Panel Switcher is extemely lightweight. (4Kb) (1Kb when minified), it doesnt attempt to perform every action under the sun like some other plugins, its clean and simply to the point, it switches content around with a few additional features and thats it. Its very lean.

# Code Sample #
When it all comes together it looks like:

```
<!-- Your Head Section -->
<link rel="stylesheet" type="text/css" media="screen" href="style/jquery.content-panel-switcher.css" /> 
<script type="text/javascript" src="js/jquery.js"></script>
<script type="text/javascript" src="js/jquery.content-panel-switcher.js"></script> 

<!--Initialize the Content Switcher, specify the speed (in milliseconds) of the transition and the panel ID you wish the content to appear in -->
<script type="text/javascript">
$(document).ready(function() {
   jcps.fader(300, '#switcher-panel');
});
</script> 

<!--The switcher buttons, basic anchor tags, with the switcher class -->
<a id="content1" class="switcher">Content 1</a> 
<a id="content2" class="switcher">Content 2</a>

<!-- The panel you wish to use to display the content -->
<div id="switcher-panel"></div>

<!-- The actual content you want to switch in and out of the panel, this is hidden -->
<div id="content1-content" class="switcher-content show">This is content 1</div>
<div id="content2-content" class="switcher-content">This is content 2</div>

```
