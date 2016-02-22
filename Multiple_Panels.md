Using multiple panels on a single page is also possible, its very similiar to using a single panel although you need to specify an additional class and parameter on the initialization string. Along with one additional initialization string per panel your using
The file multiple frame.html located in code samples directory, contains the basic code to help understand how to use this plugin with multiple panels. Most of the standard HTML markup and styling has been removed to help reduce confusion.

# Components #
Setup for a multi panel switcher is similiar to the basic 1 panel switcher, how ever an additional set class must be assigned to the buttons and the hidden content blocks.
Consider this set class as identifying which panel we want the buttons and content blocks to target.
Simply put, when the page loads, we specify which panels we want to use on the page, and we assign the set name we want to assign to the panel. Then it's simply a matter of adding the set class name to the buttons and content blocks.

If your confused, just read the code sample in either the multiple frame.html file or the code snip below and it should clear things up.

# Code Sample #
```
<link rel="stylesheet" type="text/css" media="screen" href="style/jquery.content-panel-switcher.css" /> 
<script type='text/javascript' src='js/jquery.js'></script> 
<script type='text/javascript' src='js/jquery.content-panel-switcher.js'></script> 

<!--Note the second initialization string, and the additional parameter specifying the set name (in class format with the . in front) -->
<script type='text/javascript'>
$(document).ready(function() {
jcps.fader(300, '#switcher-panel', '.set1');
jcps.slider(500, '#switcher-panel2', '.set2');
});
</script> 

<!--These are the first set of switcher buttons -->
<a id="content1" class="switcher set1">Content 1</a> 
<a id="content2" class="switcher set1">Content 2</a> 

<!-- These are the second set of switcher buttons -->
<a id="content2" class="switcher set2">Content 3</a> 
<a id="content3" class="switcher set2">Content 4</a> 

<!--These are the panels where your content will appear -->
<div id="switcher-panel"></div>
<div id="switcher-panel2"></div>

<!--These are your actual content blocks, they're hidden from the end user -->
<div id="content1-content" class="switcher-content set1 show">This is content 1</div>
<div id="content2-content" class="switcher-content set1">This is content 2</div>

<!--These are your actual content blocks, they're hidden from the end user -->
<div id="content1-content" class="switcher-content set2 show">This is content 3</div>
<div id="content2-content" class="switcher-content set2">This is content 4</div>
```

# But Wait .. #
What is that extra show class on the content1-content div? If you wish to have some content display as the default content in the panel when the page loads, simply add the show class to the end of the div class list. This is purely optional, but not everyone wants a blank page to load.

# Additional Transition Types #
You might notice the initialization string says jcps.fader, this fades the content in and out, but if you would prefer to slide the content in and out change this string to say jcps.slider instead