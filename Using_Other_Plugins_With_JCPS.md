# Using Other Plugins With JCPS #
You may wish to use other plugins such as Fancybox or Shadowbox to display photos in the hidden panels, and have them pop up when people click on them.

Initially you may find that the plugins do not work, and have no effect.

The reason for this is due to the fact that the Content Panel Switcher is doing just as its name suggests, switching content around on the page.
The problem with this is that when you initialize your fancy blog or other plugin on page load, it registers where the elements are, in the DOM, although as soon as you switch the content around using JCPS, it looses track of where the element have gone.

The solution to this is to use the jQuery Live() function.
Found here: http://api.jquery.com/live/

The Live() function simply allows jQuery to keep track of where things are.  In the example below, we call the Live() function and hand it the Fancybox initialization command instead of running it by its self in the $(document).ready()

# Example #
Here is an example of how to implement the Live() function for the jQuery Fancybox plugin.



**Without The Live() Function**
```
	$("a.fb").fancybox();

```




**With The Live() Function**
```
	$("a.fb").live('click', function(){ 
		$(this).fancybox();
	});
```


**Full Script Block Example**
```
<script type='text/javascript'>
$(document).ready(function() {
	jcps.fader(300, '#switcher-panel');

	$("a.fb").live('click', function(){ 
		$(this).fancybox();
	});
});
</script>  
```

Some plugins may not work properly like this, and may require a second click in order for the plugin to work.   This is because the first click initialized the plugin, but does not trigger the effect.
The second click triggers the effect as the plugin is then initialized.

A quick hack to get around this is to retrigger the cick event like so

**Retrigger The Click Event**
```
	$("a.fb").live('click', function() {
		$(this).fancybox().click();
	});
```

Keep in mind, this isnt the more effecient way of doing things.   It does work, but I wouldn't recommend doing this for pages with lots of links that will trigger the plugin as your effectively re-initializing the plugin on each click.   Not such a big deal for a small image gallery, but not great for page full of links that trigger the plugin.