# finality 
768p :heavy_check_mark: 1080p :heavy_check_mark: 1440p :heavy_check_mark: 4k (150%) :heavy_check_mark: Mobile :heavy_check_mark: TV Mode :soon:

Jellyfin Theme CSS (Finishing up TV mode, just waiting for logo support)

![g2](https://github.com/user-attachments/assets/580d20dd-58ee-4379-81bc-cda9b35c245d)

For the black & white version, paste this into your Custom CSS Box

```css
@import url("https://cdn.jsdelivr.net/gh/tedhinklater/finality@main/finality.css");

```

or, import the colour version with

```css

@import url("https://cdn.jsdelivr.net/gh/tedhinklater/finality@main/Finality-Coloured.css");

```

<img src="https://github.com/tedhinklater/finality/assets/66086488/1cea8ffe-6edf-451e-87f1-097a9c1803e7" width="49.5%" height="49.5%" /> <img src="https://github.com/user-attachments/assets/10470906-cd0c-4817-8280-5758da259d96" width="49.5%" height="49.5%" />
<img src="https://github.com/user-attachments/assets/21309331-27e6-4696-8103-57b96ff7f681" width="49.5%" height="49.5%" /> <img src="https://github.com/user-attachments/assets/5396b1ef-11e5-4859-8ccb-9b0d04c74f23" width="49.5%" height="49.5%" />

# Player 

![14](https://github.com/tedhinklater/finality/assets/66086488/84d70061-5216-4921-bff0-fbb25de59cca)

# Mobile

![mobile](https://github.com/tedhinklater/finality/assets/66086488/a0fb2aec-2794-4d68-b96c-9a144844729a)

Make sure you enable backdrops and under Display settings use the Dark theme
![Backdrops](https://i.imgur.com/18D9IO3.png)

# Featured Content Bar

![image](https://github.com/user-attachments/assets/30b10fa5-508d-4652-9de1-cc92e9a07d82)


*Thanks to* [*BobHasNoSoul*](https://github.com/BobHasNoSoul) and [*SethBacon*](https://forum.jellyfin.org/u-sethbacon)

1. Download [slideshow.html](https://github.com/tedhinklater/finality/blob/main/slideshow.html)

2. Enter your ```UserId``` into line 11 of slideshow.html (Get your UserID by going to the Jellyfin Dashboard, go to the Users tab, click your username. Your UserId is the last string in the address bar after the = sign)

3. Enter your ```API key``` into line 12 of slideshow.html (Go to Dashboard, API Keys tab, click the + and create a key for FeaturedSlideshow)

4. Go to your ```jellyfin-web``` folder (C:\Program Files\Jellyfin\Server\jellyfin-web) and create a folder named ```avatars``` and drop ```slideshow.html``` in that folder

5. (Important: Open Notepad with Administrator rights, or use Notepad++ for this) In the jellyfin-web folder, open the file ```home-html.RANDOMSTRINGHERE.chunk.js```

6. Ctrl+F and search for ```data-backdroptype="movie,series,book">``` 

7. Paste this after the >

```html
<style>.featurediframe { width: 89vw; height: 300px; display: block; border: 1px solid #000; margin: 0 auto}</style> <iframe class="featurediframe" src="/web/avatars/slideshow.html"></iframe>
```
8. Save the file.

9. Add this to your Custom CSS box in the Dashboard

```css
@import url("https://cdn.jsdelivr.net/gh/tedhinklater/finality@main/slideshow.css");
```

10. Empty your browser's cached web content (Ctrl+F5 or empty it from your browser's Cookies and Site Data settings section)

That's it.

# Customization
<img src="https://i.imgur.com/5d4W3M2.png" width="10%" height="10%"  />

## Changing your finality logo

Go into your Jellyfin servers custom ccs and insert this (changing the obvious part):
```css
/*Use your own header logo*/
.pageTitleWithDefaultLogo {
  background-image: url(YOURURLHERE);
}
```

## Add custom logo to login page:

![image](https://github.com/user-attachments/assets/6dd42918-bfb0-4b1a-aa72-7016a398fff2)


*Thanks to* [*BobHasNoSoul*](https://github.com/BobHasNoSoul)

### Steps

1. Enter your jellyfin web directory, on Windows this is located at your Jellyfin install location in the folder `jellyfin-web`
2. Locate the files that are named `session-login-index-html.*.bundle.js` (the * will be replaced with a random string so just find yours) there will be two
3. Open both of these files with your favorite text editor
4. Using the search function in your text editor find the string:
   ```html
   <div class="padded-left padded-right padded-bottom-page margin-auto-y">
   ```
5. In **BOTH** files replace the string with this string (replacing the obvious part):
   ```html
   <img src="YOURURLHERE" width=350px style="padding: 0px;display:block; margin-left: auto; margin-right: auto;">
   ```
6. Save your files
7. Refresh your browser with Ctrl + F5

