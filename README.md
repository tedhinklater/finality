# finality 
768p :heavy_check_mark: 1080p :heavy_check_mark: 1440p :heavy_check_mark: 4k (150%) :heavy_check_mark: Mobile :heavy_check_mark: TV Mode :soon:

Jellyfin Theme CSS (Finishing TV mode, just waiting for logo support)

![g2](https://github.com/user-attachments/assets/31ee83a0-82ff-468b-bd9c-488deaa0f2e3)

For the black & white version, paste this into your Custom CSS Box

```css
@import url("https://cdn.jsdelivr.net/gh/tedhinklater/finality@main/finality.css");

```

or, import the colour version with

```css

@import url("https://cdn.jsdelivr.net/gh/tedhinklater/finality@main/Finality-Coloured.css");

```

<img src="https://github.com/user-attachments/assets/8ba117df-0786-4dd1-aff2-3cabfef810a8" width="49.5%" height="49.5%" /> <img src="https://github.com/user-attachments/assets/85eec5f9-981a-4f5f-8a66-8b8a83aca49f" width="49.5%" height="49.5%" /> 
<img src="https://github.com/user-attachments/assets/fada2cad-a0f9-428d-a096-09f66d5244b3" width="49.5%" height="49.5%" /> <img src="https://github.com/user-attachments/assets/397eef5d-0c1b-4f56-b6ed-17191815a04e" width="49.5%" height="49.5%" />
<img src="https://github.com/user-attachments/assets/f3cdb88e-ab2f-41df-8dfc-0751d0ec1d04" width="49.5%" height="49.5%" /> <img src="https://github.com/user-attachments/assets/f1c48420-a1ed-45f6-b8c2-52ba7a4abc15" width="49.5%" height="49.5%" /> 

# Player 
![14](https://github.com/tedhinklater/finality/assets/66086488/84d70061-5216-4921-bff0-fbb25de59cca)

# Mobile
![mobile](https://github.com/tedhinklater/finality/assets/66086488/a0fb2aec-2794-4d68-b96c-9a144844729a)

Under "Display" make sure you enable backdrops and use the Dark theme

![darkbackdrops](https://github.com/user-attachments/assets/b69b1143-22c1-48df-b8e5-5aaa1869a97f)

# Optional Mods & Customization

## [Featured Content Bar](https://github.com/BobHasNoSoul/jellyfin-mods/blob/main/10.9.x.md#featured-content-bar-109xx) by [BobHasNoSoul](https://github.com/BobHasNoSoul) and [SethBacon](https://forum.jellyfin.org/u-sethbacon)

![featured](https://github.com/user-attachments/assets/c214cc03-9240-40c9-b7e1-9c3dc0634606)

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

## Changing your Jellyfin logo --> <img src="https://i.imgur.com/5d4W3M2.png" width="10%" height="10%"  /> 

Go into your Jellyfin server's Custom CSS and insert this (changing the obvious part):

```css
/*Use your own header logo*/
.pageTitleWithDefaultLogo {
  background-image: url(LOGO-URL-HERE);
}
```

## Scrolling Backdrop

```css
@import url("https://cdn.jsdelivr.net/gh/tedhinklater/finality@main/scrolling%20backdrop.css");

```

## ![Custom logo on login page](https://github.com/BobHasNoSoul/jellyfin-mods/blob/main/10.9.x.md#adding-your-logo-at-the-top-of-the-login-page-109x)

![login logo](https://github.com/user-attachments/assets/2f102c41-0632-402f-8c65-0b15eb9bb3c9)

