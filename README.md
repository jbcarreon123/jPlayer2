# jPlayer2
A no-nonsense modern web player, designed for the indie web.
Based on [duducat-music-player](https://github.com/ducdat0507/stuff/tree/main/music-player).

![image](https://github.com/user-attachments/assets/02999760-ecbd-485e-9e1b-b706838e67eb)
![image](https://github.com/user-attachments/assets/dd0b16bf-e2b8-4f38-a2fb-a81cbc31180b)

## Demo!
### https://jbcarreon123.github.io/jPlayer2/

## Features
- Easy installation and maintinance, no JS modifications required!
- Add tracks like the HTML `<audio>` tag, just add `<source>` inside the `<player-container>` element and you're good to go!
- Support for tracker files, from Modtracker, to Impulse Tracker, using the custom `<Tracker>` element
- Support for the MediaSession API, ensuring that viewers can see the now playing track system-wide

## Installation
To add jPlayer2 on your site, firstly download the `jPlayer2.js` and `jPlayer2.css`, and add the script on the top inside your site's `<body>` like this:
```html
<body>
    <script src="/where/is/jPlayer2.js"></script>
    <link rel="stylesheet" href="/where/is/jPlayer2.css">
</body>
```

Then, add it on anywhere on your site, and also specify where is the CSS file, you can also provide a fallback image:
```html
<player-container
    title="My Music Player"
    css="/where/is/jPlayer2.css"
    fallback"/fallback.png"
    id="player"
>
    <!-- Playlist tracks here -->
</player-container>
```

To add songs, just add a `<source>` tag inside `<player-container>`:
```html
<player-container
    title="My Music Player"
    css="/where/is/jPlayer2.css"
    fallback"/fallback.png"
    id="player"
>
    <source
        src="/music/song1.mp3"
        title="Never Gonna Give You Up"
        artist="Rick Astley"
        album="Whenever You Need Somebody"
        art="/test.png"
    />
</player-container>
```
> Note: Providing the metadata isn't required (the player would automatically fetch the ID3 metadata for you), but you can provide extra stuff with providing the metadata.

## Tracker files
To have support for tracker files, download the `chiptune2.js` library found here and the `libopenmpt` library found here (note: download the Web version!), and add it above the jPlayer JS import (make sure it's on this order or it won't work!):
```html
<body>
    <script src="/where/is/libopenmpt.js"></script>
    <script src="/where/is/chiptune2.js"></script>
    <script src="/where/is/jPlayer2.js"></script>
    <!-- other stuff -->
</body>
```

Then, add a `<source>` tag inside `<player-container>`:
```html
<player-container
    title="My Music Player"
    css="/where/is/jPlayer2.css"
    fallback"/fallback.png"
    id="player"
>
    <source
        src="/music/song1.mp3"
        title="Never Gonna Give You Up"
        artist="Rick Astley"
        album="Whenever You Need Somebody"
        albumArt="/test.png"
    />
    <source
        src="/music/eek.it"
        title="eek!"
        artist="Surasshu"
        albumArt="/test.png"
    />
</player-container>
```

## Solo Track mode
We also have support for single track only, without the playlist panel obstructing view! Just add the `solo="true"` attribute on the `<player-container>` tag:
```html
<player-container
    title="My Music Player"
    css="/where/is/jPlayer2.css"
    fallback"/fallback.png"
    id="player"
    solo="true"
>
    <source
        src="/music/song1.mp3"
        title="Never Gonna Give You Up"
        artist="Rick Astley"
        album="Whenever You Need Somebody"
        albumArt="/test.png"
    />
</player-container>
```

## FAQ
### How can I autoplay music on jPlayer?
For accessibility reasons, I decided to not support native autoplay on jPlayer2, so there will be no `autoplay` attribute. But if you wish, you can just hook to the `loaded` event of the player and just do play status there.
### I'm using Neocities with a free account, and can't seem to load jPlayer2 or the audio files.
If you're using Neocities with a free account beyond 2024, you will discover a Content Security Policy error that prevents you from loading the player or the audio files.
There are some solutions for this:
- Host the files straight from your Neocities site, but that means you will lose Tracker support because tracker files is not on the approved file types for free Neocities accounts,
- Switch to another web host that doesn't have this issue, like Nekoweb or GitHub pages if you need tracker support,
- Use a file hosting platform like file.garden (which I don't recommend doing), or
- Get Neocities' supporter plan, which removes the CSP and file type limitations.
