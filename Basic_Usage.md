# Components #
The most basic use is a single panel, like what this page is. There are 4 main components to a simple page like this, those are:
The switcher buttons, typically a simple <a> tag, with a unique ID of your choice, and the switcher class applied.<br>
Eg <a>home<a>
The content its self, contained in a DIV or a SPAN, with the switcher-content class applied. This class will hide these elements. These must also have a unique ID which matches the name of the switcher buttons ID, with -content added after<br>
<pre><code>&lt;div id="home-content" class="switcher-content"&gt;Some content here&lt;div&gt;<br>
</code></pre>
The the panel you wish you have your content appear in, typically in a central position on the page, like the one your reading now, this must have a unique ID, which you can choose<br>
<pre><code>&lt;div id="switcher-content" &gt;&lt;div&gt;<br>
</code></pre>

The initialization function in the header that tells the plugin what content panel you wish to use, and what speed you wish it to transition at. This must be wrapped in a jQuery $(document).ready block<br>
Eg jcps.fader(300, '#switcher-demo-panel');<br>
<br>
<h1>Code Sample</h1>
When it all comes together it looks like:<br>
<br>
<pre><code>&lt;!-- Your Head Section --&gt;<br>
&lt;link rel="stylesheet" type="text/css" media="screen" href="style/jquery.content-panel-switcher.css" /&gt; <br>
&lt;script type="text/javascript" src="js/jquery.js"&gt;&lt;/script&gt;<br>
&lt;script type="text/javascript" src="js/jquery.content-panel-switcher.js"&gt;&lt;/script&gt; <br>
<br>
&lt;!--Initialize the Content Switcher, specify the speed (in milliseconds) of the transition and the panel ID you wish the content to appear in --&gt;<br>
&lt;script type="text/javascript"&gt;<br>
$(document).ready(function() {<br>
   jcps.fader(300, '#switcher-panel');<br>
});<br>
&lt;/script&gt; <br>
<br>
&lt;!--The switcher buttons, basic anchor tags, with the switcher class --&gt;<br>
&lt;a id="content1" class="switcher"&gt;Content 1&lt;/a&gt; <br>
&lt;a id="content2" class="switcher"&gt;Content 2&lt;/a&gt;<br>
<br>
&lt;!-- The panel you wish to use to display the content --&gt;<br>
&lt;div id="switcher-panel"&gt;&lt;/div&gt;<br>
<br>
&lt;!-- The actual content you want to switch in and out of the panel, this is hidden --&gt;<br>
&lt;div id="content1-content" class="switcher-content show"&gt;This is content 1&lt;/div&gt;<br>
&lt;div id="content2-content" class="switcher-content"&gt;This is content 2&lt;/div&gt;<br>
<br>
</code></pre>

<h1>But Wait ..</h1>
What is that extra show class on the content1-content div? If you wish to have some content display as the default content in the panel when the page loads, simply add the show class to the end of the div class list. This is purely optional, but not everyone wants a blank page to load.<br>
<br>
<h1>Additional Transition Types</h1>
You might notice the initialization string says jcps.fader, this fades the content in and out, but if you would prefer to slide the content in and out change this string to say jcps.slider instead