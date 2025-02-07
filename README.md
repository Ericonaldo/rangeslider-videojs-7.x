IMPORTANT!
==================
RangeSlider port for Videojs version 7.x. (Previous version only supports vesion 5.x)

Rangeslider-videojs
==================
## Ranger Slider Plugin for Video JS Player

rangeslider.js is a plugin for Video JS player. The aim of this plugin is to create range slider to select a region of a video in video-js.

## A previous Live-Demo (Working for VideoJs 5.x)
<a href="http://acpmasquerade.github.io/rangeslider-videojs/demo/index.html" target="_blank">
    http://acpmasquerade.github.io/rangeslider-videojs/demo/index.html
</a>

## Installation

Add rangeslider.min.js and rangeslider.min.css CDN distributed file to your head tag, just after
videojs:

```html
<html>
	<head>
		<!--Latest VideoJS (5.x) -->
		<link rel='stylesheet' type='text/css' href='http://vjs.zencdn.net/5.8.7/video-js.css' >
		<script src='http://vjs.zencdn.net/5.8.7/video.js'></script>
		<!--RangeSlider Plugin-->
		<script src='src/rangeslider.js'></script>
		<link rel='stylesheet' type='text/css' href='src/rangeslider.css'>
	</head>
	<body>
		...
```

## Usage

Load a video in video-js, as you can see in the [tutorial of video-js player](https://github.com/videojs/video.js/blob/master/docs/setup.md) 

```html
<video id="vid1" class="video-js vjs-default-skin" controls preload="none" width="640" height="264"
poster="http://video-js.zencoder.com/oceans-clip.png"
data-setup=''>
	<source src="my-video.mp4" type='video/mp4' />
	<source src="my-video.webm" type='video/webm' />
	<source src="my-video.ogv" type='video/ogg' />
</video>
```
	
In addition, to load and control the plugin from Javascript must add a few lines of javascript like:

```js
var options = {},
	mplayer = videojs("vid1"),
	mplayer.rangeslider(options);
```

The first one was to load the videojs player and the second one is to load the rangeslider plugin
You can specify to the plugin to be loaded with the range slider open, the panel time, etc.. with the initial options. For example:

locked = true/false;
hidden = true/false;
panel = true/false;
controlTime = true/false;

```js
var options = {locked:true,controlTime:false}, //This will lock the range slider and won't show the control time panel to set the position of the arrows
	mplayer=videojs("vid1"),
	mplayer.rangeslider(options); 
```
	
#API Methods

Once the plugin is started, we can control the range slider with the following functions:

## # showSlider() ## #

Show the Slider Bar Component

```js
	mplayer.showSlider();
```

## # hideSlider() ## #

Hide the Slider Bar Component

```js
	mplayer.hideSlider();
```

## # showSliderPanel() ## #

Show the Panel above the arrow with the current position

```js
	mplayer.showSliderPanel();
```

## # hideSliderPanel() ## #

Hide the Panel above the arrow with the current position

```js
	mplayer.hideSliderPanel();
```

## # showControlTime() ## #

Show the panel to edit the time for the start and end arrows

```js
	mplayer.showControlTime();
```

## # hideControlTime() ## #

Hide the panel to edit the time for the start and end arrows

```js
	mplayer.hideControlTime();
```

## # lockSlider() ## #

Lock the Slider bar and it will not be possible to change the arrow positions

```js
	mplayer.lockSlider();
```

## # unlockSlider() ## #

Unlock the Slider bar and it will be possible to change the arrow positions

```js
	mplayer.unlockSlider();
```

## # setValueSlider() ## #

Set a values in seconds for the position of the arrows.

```js
	mplayer.setValueSlider(start,end);
```

## # playBetween() ## #

The video will be played in a selected section. It is necessary to enter the start and end second.

```js
	mplayer.playBetween(start, end);
```

## # loopBetween() ## #

The video will be looped in a selected section. It is necessary to enter the start and end second.

```js
	mplayer.loopBetween(start, end);
```

## # getValueSlider() ## #

Get the Values of the arrows in second.

```js
	mplayer.getValueSlider();
```


##  EVENTS


## # loadedRangeSlider `EVENT`

> Fired when the plugin has been loaded

```js
	mplayer.on("loadedRangeSlider",function() {
		//init
		...
	});
```

## # sliderchange `EVENT`
> Fired when the values of slider have changed

```js
	mplayer.on("sliderchange",function() {
		var values = mplayer.getValueSlider();
		...
	});
```
