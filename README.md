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

<img src="https://github.com/user-attachments/assets/c3c41440-6ed4-4f76-9802-9285e0cfd436" width="49.5%" height="49.5%" /> <img src="https://github.com/user-attachments/assets/8038c54b-d265-4ce1-81a3-a22457e15a3a" width="49.5%" height="49.5%" /> 
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

![featured](https://github.com/user-attachments/assets/8cc958f4-c536-40c9-9eaa-7245c08e3ed2)

1. Download [spotlight.html](https://github.com/tedhinklater/finality/blob/main/spotlight.html)

2. Go to your ```jellyfin-web``` folder (C:\Program Files\Jellyfin\Server\jellyfin-web) and create a folder named ```avatars``` and drop ```spotlight.html``` in that folder

3. (Important: Open Notepad with Administrator rights, or use Notepad++ for this) In the jellyfin-web folder, open the file ```home-html.RANDOMSTRINGHERE.chunk.js```

4. Ctrl+F and search for ```data-backdroptype="movie,series,book">``` 

5. Paste this after the >

```html
<style>.featurediframe { width: 93vw; height: 350px; display: block; border: 0px solid #000; margin: 0 auto; margin-bottom: 40px}</style><iframe class="featurediframe" src="/web/avatars/spotlight.html"></iframe>
```
6. Save the file.

7. In the same folder (jellyfin-web) open ```index.html``` with a text editor and find ```<\body><\html>``` and replace it with

```js
<script>
// Function to save credentials to sessionStorage
function saveCredentialsToSessionStorage(credentials) {
  try {
    // Store the credentials in sessionStorage
    sessionStorage.setItem('json-credentials', JSON.stringify(credentials));
    console.log('Credentials saved to sessionStorage.');
  } catch (error) {
    console.error('Error saving credentials:', error);
  }
}

// Function to save the API key to sessionStorage
function saveApiKey(apiKey) {
  try {
    sessionStorage.setItem('api-key', apiKey);
    console.log('API key saved to sessionStorage.');
  } catch (error) {
    console.error('Error saving API key:', error);
  }
}

// Override the default console.log function
(function() {
  var originalConsoleLog = console.log;

  console.log = function(message) {
    // Call the original console.log method
    originalConsoleLog.apply(console, arguments);

    // Check if the message contains the JSON credentials
    if (typeof message === 'string' && message.startsWith('Stored JSON credentials:')) {
      try {
        // Extract the JSON credentials from the message
        var jsonString = message.substring('Stored JSON credentials: '.length);
        var credentials = JSON.parse(jsonString);

        // Save the credentials to sessionStorage
        saveCredentialsToSessionStorage(credentials);
      } catch (error) {
        console.error('Error parsing credentials:', error);
      }
    }

    // Check if the message contains the WebSocket URL with api_key
    if (typeof message === 'string' && message.startsWith('opening web socket with url:')) {
      try {
        // Extract the API key from the message
        var url = message.split('url:')[1].trim();
        var urlParams = new URL(url).searchParams;
        var apiKey = urlParams.get('api_key');

        if (apiKey) {
          saveApiKey(apiKey);
        }
      } catch (error) {
        console.error('Error extracting API key:', error);
      }
    }
  };
})();
</script>
</body></html>
```
And Save. 

8. Empty your browser's cached web content (Ctrl+F5 or empty it from your browser's Cookies and Site Data settings section)

9. That's it.

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

