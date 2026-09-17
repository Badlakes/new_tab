# Personal Firefox New Tab

A lightweight start page with a GIF wallpaper, shortcut icons, and automatic favicons. The whole project — the extension and the Firefox interface customization included — was made with **Firefox** in mind.

**Live preview:** [badlakes.github.io/new_tab](https://badlakes.github.io/new_tab/)

## Project structure

- `index.html` — the start page. Edit the JSON list at the end of this file to manage shortcuts.
- `background.gif` — the wallpaper shown behind the shortcuts.
- `extensao-firefox/` — the Firefox-specific new-tab extension.

## 1. Publish the start page with GitHub Pages

1. Push this repository to GitHub.
2. Open the repository on GitHub, then go to **Settings → Pages**.
3. Under **Build and deployment**, select the `main` branch and the `/ (root)` folder, then save.
4. GitHub will publish the page at a URL similar to:

   `https://YOUR-USERNAME.github.io/REPOSITORY-NAME/`

For this repository, the page is available at:

`https://badlakes.github.io/new_tab/`

### Updating the page

Edit `index.html` or replace `background.gif`, then publish the changes:

```powershell
git add .
git commit -m "Update new tab"
git push
```

GitHub Pages updates automatically after the push.

### Editing shortcuts

At the bottom of `index.html`, edit the JSON array. Each shortcut needs a display name and a URL:

```json
{ "nome": "GitHub", "url": "https://github.com" }
```

Favicons are fetched automatically from the shortcut domain. The page must have an internet connection for them to load.

## 2. Enable the Firefox extension

The extension is built specifically for Firefox. It replaces Firefox's new-tab page and displays the GitHub Pages site. It also loads the GIF wallpaper reliably inside the extension.

1. Disable **New Tab Override** or any other Firefox extension that replaces the new-tab page.
2. Open `about:debugging#/runtime/this-firefox` in Firefox.
3. Click **Load Temporary Add-on…**.
4. Select `extensao-firefox/manifest.json` from this project.
5. Open a new Firefox tab with `Ctrl+T`.

The temporary extension is removed when Firefox closes. To install it permanently in standard Firefox, package and sign it through Mozilla Add-ons as an **unlisted** extension.

Changes to the website only need a GitHub push. Reload the extension from `about:debugging` only after changing files inside `extensao-firefox/`.

## 3. Hide the Firefox extension label (optional)

Firefox shows an **Extension** label in the address bar for extension pages. This is a Firefox security indicator and cannot be removed by the extension itself, but it can be hidden locally with Firefox UI CSS.

1. Open `about:config` in Firefox and set `toolkit.legacyUserProfileCustomizations.stylesheets` to `true`.
2. Open `about:profiles`, find the active Firefox profile, and click **Open Folder**.
3. Create a folder named `chrome` in that profile folder.
4. Create `chrome/userChrome.css` with the following content:

```css
#identity-box.extensionPage {
  display: none !important;
}
```

5. Restart Firefox.

This is only a visual Firefox customization. Firefox updates can change its interface and may require the rule to be adjusted.
