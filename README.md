tween.js
========

#### Javascript Tweening Engine ####

[![Flattr this](https://api.flattr.com/button/flattr-badge-large.png)](https://flattr.com/thing/45014/tween-js)

Super simple, fast and easy to use tweening engine which incorporates optimised Robert Penner's equations.

[Contributors](http://github.com/sole/tween.js/contributors)

### Examples ###

[![Dynamic to](http://sole.github.com/tween.js/assets/examples/07_dynamic_to.png)](http://sole.github.com/tween.js/examples/07_dynamic_to.html)
[![Array interpolation](http://sole.github.com/tween.js/assets/examples/03_graphs.png)](http://sole.github.com/tween.js/examples/06_array_interpolation.html)
[![Video and time](http://sole.github.com/tween.js/assets/examples/06_video_and_time.png)](http://sole.github.com/tween.js/examples/05_video_and_time.html)
[![Simplest possible example](http://sole.github.com/tween.js/assets/examples/04_simplest.png)](http://sole.github.com/tween.js/examples/04_simplest.html)
[![Graphs](http://sole.github.com/tween.js/assets/examples/03_graphs.png)](http://sole.github.com/tween.js/examples/03_graphs.html)
[![Black and red](http://sole.github.com/tween.js/assets/examples/02_black_and_red.png)](http://sole.github.com/tween.js/examples/02_black_and_red.html)
[![Bars](http://sole.github.com/tween.js/assets/examples/01_bars.png)](http://sole.github.com/tween.js/examples/01_bars.html)
[![hello world](http://sole.github.com/tween.js/assets/examples/00_hello_world.png)](http://sole.github.com/tween.js/examples/00_hello_world.html)

### Projects using tween.js ###

[![Minesweeper 3D](http://sole.github.com/tween.js/assets/projects/06_minesweeper3d.png)](http://egraether.com/mine3d/)
[![ROME](http://sole.github.com/tween.js/assets/projects/05_rome.png)](http://ro.me)
[![WebGL Globe](http://sole.github.com/tween.js/assets/projects/04_webgl_globe.png)](http://data-arts.appspot.com/globe)
[![Androidify](http://sole.github.com/tween.js/assets/projects/03_androidify.png)](http://www.androidify.com/)
[![Floweroscope](http://sole.github.com/tween.js/assets/projects/02_floweroscope.png)](http://www.floweroscope.com/)
[![The Wilderness Downtown](http://sole.github.com/tween.js/assets/projects/01_wilderness.png)](http://thewildernessdowntown.com/)
[![Linechart](http://sole.github.com/tween.js/assets/projects/00_linechart.png)](http://dejavis.org/linechart)

### Usage ###

Download the [minified library](http://github.com/sole/tween.js/raw/master/build/Tween.js) and include it in your html.

```html
<script src="js/tween.min.js"></script>
```

The following code creates a Tween which will change the `x` attribute in a position variable, so that it goes from 50 to 400 in 2 seconds. The anonymous function set up with an interval will update the screen so that we can see something happening:

```html
<script>

	init();
	animate();

	function init() {

		var output = document.createElement( 'div' );
		output.style.cssText = 'position: absolute; left: 50px; top: 300px; font-size: 100px';
		document.body.appendChild( output );

		var tween = new TWEEN.Tween( { x: 50, y: 0 } )
			.to( { x: 400 }, 2000 )
			.easing( TWEEN.Easing.Elastic.InOut )
			.onUpdate( function () {

				output.innerHTML = 'x == ' + Math.round( this.x );
				output.style.left = this.x + 'px';

			} )
			.start();

	}

	function animate() {

		requestAnimationFrame( animate ); // js/RequestAnimationFrame.js needs to be included too.
		TWEEN.update();

	}

</script>
```

Note: this corresponds to the example [04_simplest.html](http://sole.github.com/tween.js/examples/04_simplest.html) that you can find in the ```examples``` folder.

Have a look at that folder to discover more functionalities of the library!

Also, Jerome Etienne has written a [tutorial](http://learningthreejs.com/blog/2011/08/17/tweenjs-for-smooth-animation/) demonstrating how to use tween.js with three.js, and it's also great for understanding how tweens work!

### FAQ ###

**How do you set a tween to start after a while?**

Use the `delay()` method: `var t = new TWEEN.Tween({...}).delay(1000);`

**Is there a jQuery plug-in?**

No, we like to keep it simple and free of dependencies. Feel free to make one yourself, though! :-)

