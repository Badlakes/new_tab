# Firefox Extension — Personal New Tab

This Firefox-specific extension replaces Firefox's new-tab page and displays the website published at:

`https://badlakes.github.io/new_tab/`

Because it loads the website inside the extension, updates pushed to GitHub Pages appear automatically. The GIF is loaded by the extension itself to avoid background issues inside the embedded page. To change the website later, edit `src` and the GIF URL in `new-tab.html`.

## Test in Firefox

1. Type `about:debugging#/runtime/this-firefox` in the address bar.
2. Click **Load Temporary Add-on…**.
3. Select this folder's `manifest.json` file.
4. Open a new tab with `Ctrl+T`.

The temporary add-on is removed when Firefox closes. To install it permanently in standard Firefox, create an `.xpi` package and have it signed through Mozilla Add-ons; it can remain **unlisted** rather than publicly listed.
