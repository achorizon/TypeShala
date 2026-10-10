# TYPSHALA Web Edition

A static, GitHub Pages-ready typing tutor inspired by the supplied legacy TYPSHALA archive. It runs with plain HTML, CSS, and JavaScript; no build step, server, account, API key, or paid service is required.

## Folder structure

```text
TYPSHALA-WEB/
├── index.html       # Main page (GitHub Pages entry point)
├── style.css        # Responsive design and styles
├── app.js           # Navigation, lessons, typing practice, speed tests, local history
├── lessons.js       # Lesson text extracted from the supplied TYPSHALA .LSN files
└── README.md        # This guide
```

## Publish on GitHub Pages

1. Extract `TYPSHALA-WEB.zip` on your computer.
2. Open the extracted `TYPSHALA-WEB` folder. The `index.html`, `style.css`, `app.js`, and `lessons.js` files must all be at the top level together.
3. Create a GitHub repository, or open the repository where you want to publish the site.
4. Upload **the files inside** `TYPSHALA-WEB` to the repository's root (do not upload only the ZIP file and do not leave everything nested in another folder unless you set that folder as the Pages publishing source).
5. In the repository, open **Settings → Pages**.
6. Under Build and deployment, choose **Deploy from a branch**, select `main` and `/(root)`, then Save.
7. Wait for GitHub Pages to publish and open the URL it provides.

No `npm install`, Node.js, Python, backend, database, or environment variables are needed. The app is designed to work on modern browsers on Windows, macOS, Linux, Android, and iOS. It should be served from GitHub Pages or opened locally as `index.html`.

## Data and offline use

- Typing history and the optional profile name are stored in the current browser using `localStorage`.
- That data stays in that browser on that device. It does not sync across devices or browsers. Clearing browser data may remove it.
- Core features run locally after the files are available. Nepali legacy lessons use a remotely hosted Preeti webfont so that the original Preeti-encoded key sequences can display as Nepali across operating systems. An internet connection is needed for that webfont; if the font host is unreachable, legacy text may appear as Latin characters. For a fully self-contained offline build, a redistributable licensed Preeti font file must be bundled.
- The legacy `.LSN` files contain keyboard-drill text; this web edition imports those drill contents. The old Windows executable's exact interface and every behavior cannot be verified from the binary alone, so this is a web recreation, not a byte-for-byte port.

## Troubleshooting

- If the page looks unstyled, make sure `style.css` is beside `index.html` and the filename casing is exact.
- If lessons do not appear, make sure `lessons.js` is beside `index.html` and was uploaded completely.
- On GitHub, upload the contents of this folder to the repository root. GitHub Pages expects `index.html` at the configured publishing root.

## Nepali Preeti course behavior

Selecting a Nepali course or a Nepali typing test automatically activates Preeti styling and uses the original legacy Preeti key sequences from the supplied `.LSN` lesson files. English course selection returns the app to normal English styling. The supplied original archive did not contain a standalone Preeti font file, so the web edition references the hosted font URL configured in `style.css`.
