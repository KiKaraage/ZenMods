## Preview on Zen 1.0.1-a.4

![image](https://github.com/user-attachments/assets/b7b7bb54-b52a-4ab8-820f-449db163c843)

## Applying "Arc Mode"

### 1) Go to Customize Toolbar menu, add Flexible Spaces and move the buttons 

- Disclaimer: Since I use this setup with Compact Mode active (either on "Hide sidebar" or "Hide both" mode), I tend to use Expand Sidebar button much less, so I won't include the button in this setup. Instead, I assign the Arc Sidebar icon for Zen's Side Panels button.
- Right click on navbar > "Customize Toolbar" (Recommended: Do this when you're not on Compact Mode)
- Add many Flexible Spaces in left and right side of URL bar. (I personally added 8 or 10 to each sides)
- Add History button beside the Side Panels button/in the left side of Workspaces button.
- Move Side Panels button to "Zen Sidebar Top Buttons" area (the one with Menu button and Expand Sidebar button)
- Move Download button beside Side Panels button, tick "Hide button when empty" option on.
- Remove Expand Sidebar button.

![image](https://github.com/user-attachments/assets/e4e14f2c-8c94-4cac-b223-18dda80ad6a6)

### 2) Applying the CSS and SVG

Put the CSS and SVG files on your `chrome` directory (`about:profiles` > Root Directory > Open Folder).
Open your `userChrome.css` file in that folder and paste the line below; save and restart Zen.

```
@import url("arcmode.css");
```

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
