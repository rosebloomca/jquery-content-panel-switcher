# Initializing The Plugin #

Initialization is done from anywhere using the jQuery $(document).ready event.
```
$(document).ready(function() {
   jcps.fader(300, '#switcher-panel');
});
```

## Options ##

  * Changing the number in the first parameter adjusts the speed of the transition. 300 milliseconds by default.   The higher the number the slower the transition.   Set this to zero to use no transition.

  * Changing from <b>jcps.fader</b> to <b>jcps.slider</b> changes the transition type.