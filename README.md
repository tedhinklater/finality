# finality



Jellyfin Theme CSS (Finishing up TV mode and Mobile, they're functional though)

![bw1](https://i.imgur.com/qaNGzGN.png)

Import with

```css
@import url("https://cdn.jsdelivr.net/gh/tedhinklater/finality@main/finality.css");

```

or, import the colour version with

```css

@import url("https://cdn.jsdelivr.net/gh/tedhinklater/finality@main/Finality-Coloured.css");

```
![c1](https://i.imgur.com/73vsPMk.png)
![c3](https://i.imgur.com/5ctM8f1.png)
![c4](https://i.imgur.com/2TcAiAb.png)

Make sure you enable backdrops and under Display settings use the Dark theme
![Backdrops](https://i.imgur.com/18D9IO3.png)

# Featured Content Bar by [BobHasNoSoul](https://github.com/BobHasNoSoul)

1) Download [slideshow.html](https://github.com/tedhinklater/finality/blob/main/slideshow.html)

2) Enter your ```UserId``` into line 11 of slideshow.html (Get your UserID by going to the Jellyfin Dashboard, go to the Users tab, click your username. Your UserId is the last string in the address bar after the = sign)

3) Enter your ```API key``` into line 12 of slideshow.html (Go to Dashboard, API Keys tab, click the + and create a key for FeaturedSlideshow)

4) Go to your ```jellyfin-web``` folder (C:\Program Files\Jellyfin\Server\jellyfin-web) and create a folder named ```avatars``` and drop ```slideshow.html``` in that folder

5) (Important: Open Notepad with Administrator rights, or use Notepad++ for this) In the jellyfin-web folder, open the file ```home-html.RANDOMSTRINGHERE.chunk.js```

6) Ctrl+F and search for ```data-backdroptype="movie,series,book">``` 

7) Paste this after the >

```html
<style>.featurediframe { width: 89vw; height: 300px; display: block; border: 1px solid #000; margin: 0 auto}</style> <iframe class="featurediframe" src="/web/avatars/slideshow.html"></iframe>
```
8) Save the file.

9) Add this to your Custom CSS box in the Dashboard

```css
@import url("https://cdn.jsdelivr.net/gh/tedhinklater/finality@main/slideshow.css");
```

10) Empty your browser's cached web content (Ctrl+F5 or empty it from your browser's Cookies and Site Data settings section)

That's it.
