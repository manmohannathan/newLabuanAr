# Supervisor demo update — 13 UMSKAL floors

See SUPERVISOR-DEMO.md for the quick presentation flow and demo-content details.

# Labuan Legends AR — interactive edition

This is an updated copy of your uploaded project. Your original ZIP and XAMPP project were not changed.

## Try it

1. Extract the supplied ZIP. Keep all folders together.
2. Copy the `Labuan-Ar` folder into your XAMPP `htdocs` folder under a new name, such as `Labuan-Ar-Interactive`, to keep your existing project.
3. Start Apache in XAMPP. On that computer, open `http://localhost/Labuan-Ar-Interactive/`.
4. Choose **Explore in 3D first** to try both actual models without camera access.
5. Choose **Open AR camera** for image tracking. Open **View the markers** and print either original marker, or show it on a second screen. Keep the image proportions, border, and full image intact.

On a phone, use your published **HTTPS** address. A plain HTTP address pointing to your computer's LAN IP generally will not permit camera access. `localhost` on the phone refers to the phone itself, not your computer. You do not need PHP, MySQL, or an app installation for this edition.

## What was added

- Landing page with an explicit camera-start button and a camera-free 3D viewer.
- A brief rising/scaling reveal for each landmark. It plays once per landmark per session and can be replayed. Losing the marker briefly does not repeatedly restart the animation.
- Thirteen selectable demo floors on the new UMSKAL model and three discovery points on the Clock Tower model. They follow the model during rotation and zoom. The Discover list provides the same content when a point is out of view or difficult to tap.
- Highlighted architectural features: UMSKAL floor bands 1–13; Clock Tower dials, roof and path.
- Three short, user-controlled story chapters per landmark, with corresponding model highlights.
- One optional challenge per landmark, with hints and visible feedback.
- A two-landmark passport. Complete all discoveries for that landmark OR answer the landmark's challenge correctly to earn its stamp. Repeated visits do not duplicate stamps.
- Mouse/touch rotation, two-finger pinch zoom, mouse-wheel zoom, bounded zoom buttons and reset view.
- English/Malay controls, discoveries, stories, questions and feedback.
- Your original UMSKAL English and Malay audio, now with pause/resume. It pauses when tracking is lost, a different landmark is selected, a story/dialog is opened, or the browser is hidden. Language changes reset it to avoid mismatched narration.
- Vintage and modern themes, remembered in the browser.
- Camera-denial recovery and clean camera shutdown on Home/page exit.

Two markers are loaded in the same MindAR session. Only the selected landmark is shown, avoiding overlapping models. If both are detected, use the landmark buttons to choose which one to explore. Separate markers and keep them clearly in frame for the best results.

Passport progress is saved on the same browser and site address. Clearing site data removes it; private browsing or disabled storage may limit it to the current session. Stamps indicate exploration in AR or the 3D viewer, not a verified physical visit. There is no account or cloud database.

## Content and scope

The UMSKAL floor descriptions are fictional sample uses for the supervisor demonstration. The 13 floor bands are evenly spaced across the exported tower shaft and crown; they are approximate and are not surveyed floor plans. Floor 1 is the lowest demo level and Floor 13 the highest, excluding the roof. The original campus information and visitor details have been retained, with a reminder to confirm visitor arrangements. They were not independently fact-checked. Clock Tower discoveries describe its uploaded model. UMSKAL discoveries demonstrate a sample floor directory. The short story chapters are an architectural tour, not newly researched folklore.

- No Clock Tower narration file was present, so its narration control is disabled with an explanation.
- The original long UMSKAL recordings remain separate from the short interactive chapters. There is no timed lip-sync or audio-to-animation synchronization.
- No animated narrator character was provided. It has not been fabricated.
- **Then and Now** is not included: historically supported earlier images or models are needed first.

## Publishing to GitHub Pages

Upload the **contents** of `Labuan-Ar` to the chosen publishing folder in your repository. `index.html` must be at that folder's root, alongside `coding`, `libs`, and `assets`. Configure that folder/branch in Settings → Pages, or use your existing Pages workflow. Use the generated HTTPS address for your QR code. Pushing files alone does not configure Pages if it is not already enabled.

All project asset links are relative and support a repository subpath. Do not rename asset files without updating their references. In particular, keep each `.gltf` beside its matching `.bin` file. Netlify static hosting also remains compatible.

Camera reference: https://developer.mozilla.org/en-US/docs/Web/API/MediaDevices/getUserMedia
GitHub Pages reference: https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site

## Where to edit

- `coding/content.js`: landmarks, discovery labels, model-part name matches, stories, questions, bilingual text and audio/marker paths.
- `coding/main.js`: tracking, reveal, gestures, audio, chapter navigation and passport behaviour.
- `coding/styles.css`: colours, themes, layout and responsive styling.
- `index.html`: landing page and interface structure.

Clock Tower model parts are matched by their existing exported node names. For UMSKAL, floorDiscovery.boundsNames identifies the main tower geometry; floor bands are generated across that height, not across the entire campus landscape. If a model is replaced, update each discovery's `match` prefixes in `content.js` to fit the new model. Model sizes are normalized automatically. The landmark count in the passport follows the configured targets.

The supplied lightweight glTF loader is preserved. It supports the included assets; it is not a replacement for a complete animated/skinned glTF loader. Adding animated characters may require extending or replacing it with a compatible official loader.

The existing single-image `.mind` files are combined into one in-memory v2 dictionary. This relies on the validated format used by the supplied files; newly compiled files with a different format should be compiled together as a supported multi-image target and the target loader updated accordingly.

There are two small compatibility changes to the bundled MindAR file: its resize callback is retained for removal when exiting, and resizing waits until its video/controller are ready. Camera startup is handled in the app so permission errors and cancellation can be recovered cleanly.

## Verification and phone checklist

Automated Chromium checks used the actual models and local assets: model loading; both original image targets through a synthetic camera stream; target loss and landmark switching; hotspot discovery and challenges; both-language controls; persistence after reload; camera denial and recovery; stream shutdown; phone, landscape and desktop layouts. No missing asset requests or uncaught page errors occurred in these checks.

This is not a physical-device certification. Before demonstrating or publishing your final submission, test the HTTPS version in Android Chrome and iPhone Safari: camera permission, both printed markers, rotation, pinch zoom, narration in both languages, target loss/reacquisition, and Home releasing the camera. Check lighting, glare, loading time and responsiveness on your actual phone.
