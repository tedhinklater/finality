# finality 
768p :heavy_check_mark: 1080p :heavy_check_mark: 1440p :heavy_check_mark: 4k :heavy_check_mark: Mobile :heavy_check_mark: TV Mode :soon:

Jellyfin Theme CSS (Finishing TV mode, just waiting for logo support)

![g2](https://github.com/user-attachments/assets/4b636138-2e50-465f-ad7c-1c71403b4d1f)

For the black & white version, paste this into your Custom CSS Box

```css
@import url("https://cdn.jsdelivr.net/gh/tedhinklater/finality@main/finality.css");

```

or, import the colour version with

```css

@import url("https://cdn.jsdelivr.net/gh/tedhinklater/finality@main/Finality-Coloured.css");

```

<img src="https://github.com/user-attachments/assets/db4d8842-d7b0-420c-881e-841ac21a0db2" width="49.5%" height="49.5%" /> <img src="https://github.com/user-attachments/assets/eb94f62f-119b-4c1e-8071-61476c8296d8" width="49.5%" height="49.5%" /> 
<img src="https://github.com/user-attachments/assets/6bba7531-bef6-4698-9e0c-6843eaa6a292" width="49.5%" height="49.5%" /> <img src="https://github.com/user-attachments/assets/13ccaeef-9ed7-4396-afde-f100ad4af2bf" width="49.5%" height="49.5%" />
<img src="https://github.com/user-attachments/assets/984a75d5-1706-48da-9f75-b3cf6ccd45b7" width="49.5%" height="49.5%" /> <img src="https://github.com/user-attachments/assets/401de20c-205f-4439-9938-b399d5462197" width="49.5%" height="49.5%" />

Ultrawide users, import a version above, and also this fix: 

```css

@import url("https://cdn.jsdelivr.net/gh/tedhinklater/finality@main/UltrawideFix.css");

```

# Player 
![Player](https://github.com/user-attachments/assets/957bbe26-eb38-4db2-a9f6-8b2311a4d943)

# Mobile
![mobile](https://github.com/tedhinklater/finality/assets/66086488/a0fb2aec-2794-4d68-b96c-9a144844729a)

Under "Display" make sure you enable backdrops and use the Dark theme

![darkbackdrops](https://github.com/user-attachments/assets/b69b1143-22c1-48df-b8e5-5aaa1869a97f)

# Optional Mods & Customization

## [Featured Content Bar](https://github.com/BobHasNoSoul/jellyfin-mods/blob/main/10.9.x.md#featured-content-bar-109xx) by [BobHasNoSoul](https://github.com/BobHasNoSoul) and [SethBacon](https://forum.jellyfin.org/u-sethbacon)

![Featured](https://github.com/user-attachments/assets/2607e73b-3ad8-4dc3-9844-a6b3c9d4be95)

1. Download [spotlight.html](https://github.com/tedhinklater/finality/blob/main/spotlight.html)

2. Enter your ```UserId``` into line 55 of spotlight.html (Get your UserID by going to the Jellyfin Dashboard, go to the Users tab, click your username. Your UserId is the last string in the address bar after the = sign)

3. Enter your ```API key``` into line 55 of spotlight.html (Go to Dashboard, API Keys tab, click the + and create a key for Spotlight)

4. Go to your ```jellyfin-web``` folder (C:\Program Files\Jellyfin\Server\jellyfin-web) and create a folder named ```avatars``` and drop ```spotlight.html``` in that folder

5. (Important: Open Notepad with Administrator rights, or use Notepad++ for this) In the jellyfin-web folder, open the file ```home-html.RANDOMSTRINGHERE.chunk.js```

6. Ctrl+F and search for ```data-backdroptype="movie,series,book">``` 

7. Paste this after the >

```html
<style>.featurediframe { width: 93vw; height: 350px; display: block; border: 0px solid #000; margin: 0 auto; margin-bottom: 40px}</style><iframe class="featurediframe" src="/web/avatars/spotlight.html"></iframe>
```
8. Save the file.

9. Empty your browser's cached web content (Ctrl+F5 or empty it from your browser's Cookies and Site Data settings section)

10. That's it. If you update your Jellyfin Server, just repeat steps 5 - 9. 

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

