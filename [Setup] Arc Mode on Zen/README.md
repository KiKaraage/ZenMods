## Preview on Zen 1.0.1-a.4

![image](https://github.com/user-attachments/assets/ac70a6b0-861b-4f94-8d3a-652da29d2db4)

### Precautions:
- This setup is made to replicate **ONLY the UI** of Arc Browser, particularly the Windows version.
- I'm not planning to add "URL bar in sidebar" since I made this setup based on Windows version of Arc.
- Want Folders? Please wait patiently until the developer(s) applied it in Zen.
- Otherwise, if you really want folders, you can use Sidebery to get vertical tab, add [this code in Sidebery's Style Editor](https://github.com/KiKaraage/ArcWTF/blob/main/sidebery-css-style), and use [this mod](https://zen-browser.app/themes/5274f79a-e648-4029-adf3-3f10dfdc0012) to hide Zen's native vertical tabs. You can't really use Zen's Workspace with Sidebery, though.
<details>
  <summary>Since Zen v1.0.1-a.5 doesn't let you move (the ellipsis) Menu button to the very left side with just CSS, that position can be achieved only with enabling Compact Mode. </summary>

  ![image](https://github.com/user-attachments/assets/e97e005f-53f8-4c6c-8a81-b60c655f614c)

  ![image](https://github.com/user-attachments/assets/53bd2abe-c1a3-43b5-9d08-85529d1d2d46)

  And there's a bug for Compact Mode: In "Hide toolbar" and "Hide both" mode, if you put Side Panels button on the top bar, the bar won't be hidden until you close the Side Panels.

  ![image](https://github.com/user-attachments/assets/c9e52ee1-9cdd-4827-adb9-30929d26963f)

</details>

## How to Apply?

### 1) Applying the CSS and SVG

- Put the CSS and SVG files on your `chrome` directory (`about:profiles` > Root Directory > Open Folder).
- Open your `userChrome.css` file in that folder and paste the line below, then save the file.

```
@import url("./arcmode.css");
```
Make sure you go to `about:config` and enable/add these configurations (as Boolean):
- `toolkit.legacyUserProfileCustomizations.stylesheets` (to enable customizations via `userChrome.css`)
- `svg.context-properties.content.enabled` (to enable similar coloring from browser toolbar buttons to our custom SVG files)
- `uc.arc.mode` (to enable custom configurations in this setup: custom icons, removing workspace icon strip backgrounds, etc)

Restart Zen afterwards.

### 2) Go to Customize Toolbar menu, add Flexible Spaces and move the buttons 

- Disclaimer: Since I use this setup with Compact Mode active (either on "Hide sidebar" or "Hide both" mode), I tend to use Expand Sidebar button much less, so I won't include the button in this setup. Instead, I assign the Arc Sidebar icon for Zen's Side Panels button.
- Right click on navbar > "Customize Toolbar" (Recommended: Do this when you're not on Compact Mode)
- Add many Flexible Spaces in left and right side of URL bar. (I personally added 8 or 10 to each sides)
- Add History button beside the Side Panels button/in the left side of Workspaces button.
- Move Side Panels button to "Zen Sidebar Top Buttons" area (the one with Menu button and Expand Sidebar button)
- Move Download button beside Side Panels button, tick "Hide button when empty" option on.
- Remove Expand Sidebar button.

![image](https://github.com/user-attachments/assets/3f7fb0d6-3a29-4021-8483-fa5ca7c5d444)

### 3) To get Arc-like Copy URL button feature...
Use this extension: [Copy Frame or Page URL](https://addons.mozilla.org/en-US/firefox/addon/copy-frame-or-page-url), go to its settings in `about:addons` (or right click the Copy extension icon > Manage Extension), go to the Options tab, enable the "Show button inside address bar" option...

![image](https://github.com/user-attachments/assets/15d88b76-ae4f-4248-9d5f-cfb481dd4405)


### 4) More beneficial code to use...
You can directly put these on your `userChrome.css` file. Modify it based on your needs.

```
/* Hide label for Zen internal pages + hide translation, bookmark, zoom level buttons */
#urlbar #identity-box.chromeUI #identity-icon-label,
#page-action-buttons #translations-button,
#page-action-buttons #star-button-box,
#page-action-buttons #urlbar-zoom-button {
  display: none !important;
}

/* Remove container label text and move its order to the very right side of URL bar */
#userContext-label {
  display: none;
}
#userContext-icons {
  order: 1;
}
```
