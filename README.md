# jPlayer2
A no-nonsense modern web player, designed for the indie web.
Based on [duducat-music-player](https://github.com/ducdat0507/stuff/tree/main/music-player).

## Features
- Easy installation and maintinance, no JS modifications required!
- Add tracks like the HTML `<audio>` tag, just add `<source>` inside the `<jPlayer>` element and you're good to go!
- Support for tracker files, from Modtracker, to Impulse Tracker, using the custom `<Tracker>` element
- Support for the MediaSession API, ensuring that viewers can see the now playing track system-wide

## Installation
To add jPlayer2 on your site, firstly download the `jPlayer2.js` and `jPlayer2.css`, and add it to your site's `<head>` like this:
```html
<head>
    <script src="/where/is/jPlayer2.js"></script>
    <link rel="stylesheet" href="/where/is/jPlayer2.css">
</head>
```

Then, add it on anywhere on your site:
```html
<jPlayer
    title="My Music Player"
    id="player"
>
    <!-- Playlist tracks here -->
</jPlayer>
```

To add songs, just add a `<source>` tag inside `<jPlayer>`:
```html
<jPlayer
    title="My Music Player"
    id="player"
>
    <source
        src="/music/song1.mp3"
        title="Never Gonna Give You Up"
        artist="Rick Astley"
        album="Whenever You Need Somebody"
        albumArt="/test.png"
    />
</jPlayer>
```

## Tracker files
To have support for tracker files, download the `chiptune2.js` library found here and the `libopenmpt` library found here (note: download the Web version!), and add it above the jTracker JS import (make sure it's on this order or it won't work!):
```html
<head>
    <script src="/where/is/libopenmpt.js"></script>
    <script src="/where/is/chiptune2.js"></script>
    <script src="/where/is/jPlayer2.js"></script>
    <!-- other stuff -->
</head>
```

Then, add a `<Tracker>` tag inside `<jPlayer>`:
```html
<jPlayer
    title="My Music Player"
    id="player"
>
    <source
        src="/music/eek.it"
        title="eek!"
        artist="Surasshu"
        albumArt="/test.png"
    />
</jPlayer>
```