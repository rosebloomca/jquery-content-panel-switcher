# Tips #

### Changing Transition Types ###
You might notice the initialization string says jcps.fader, this fades the content in and out, but if you would prefer to slide the content in and out change this string to say jcps.slider instead


### Setting Default Content ###
If you wish to have some content display as the default content in the panel when the page loads, simply add the show class to the end of the div class list. This is purely optional, but not everyone wants a blank page to load.


### Eliminating Strange Resizing Issue ###
Depending on your CSS, and layout, using the Slider transition may cause the panel to jump in size then snap back like an elastic band. To prevent this, give the containing element or the panel a fixed height, this will prevent the panel causing any strange resizing issues.