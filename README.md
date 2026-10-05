# Sprite Review

A browser viewer for Corey's video game GIF references. The app contains no GIFs and sends no GIFs to GitHub. It reads a folder the user chooses in Chrome or Edge and saves review choices in that folder.

## Library

The private library is `My Drive/Creative Work/Sprite Review` in Google Drive. It contains `Source/`, the preexisting `Keep/` folder, and a `review-decisions.json` file created by the app after the first review choice. The original desktop folder at `C:\Users\Corey\Desktop\spritesorter` is preserved.

On either computer, install Google Drive for desktop and sign in to the same Google account. Wait until `Sprite Review/Source` appears in the local Google Drive folder. Open the published Sprite Review page in Chrome or Edge, click **Choose synced folder**, and select **Sprite Review** (the folder containing `Source`). The browser may ask for folder read and write access.

Use the folder and status controls to narrow the GIFs. Select one to view its animation. Press K for Keep, P for Pass, or U to clear a choice. The app never moves or deletes the GIFs. Choices are stored in `review-decisions.json` and synced by Google Drive. The Export decisions button downloads a backup copy.

Review from one computer at a time; let Google Drive finish syncing before switching computers. Click Refresh on the second computer to load the latest choices.

## Design

The site is one static HTML file with no build step or external scripts. GitHub Pages hosts only this file and this README. The browser uses the File System Access API to read local files chosen by the user. Because that API is not available in every browser, Chrome or Edge is required for the folder picker. The app needs HTTPS when hosted.

The old Flask viewer is left untouched for reference. Its `app.run()` line is commented out and its template variables do not match the Python route, which explains the loading failure.
