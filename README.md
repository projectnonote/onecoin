# Coinfolio for OneNote

Coinfolio is a OneNote task pane add-in for keeping a visual numismatic album. Add coin photos and details to sleeves, then insert the album chart into the active OneNote page.

## Publish with GitHub Pages

This project is configured to publish as a static site with GitHub Pages. The published add-in site is public on the internet, so do not add secrets or private data to this repository. Coin entries are kept in browser local storage; the app does not send them to GitHub.

1. Create a **public** GitHub repository named `onecoin`.
2. In `manifest.xml`, replace every occurrence of `YOUR-GITHUB-USERNAME` with your GitHub username. Keep the repository name `onecoin` in the URLs.
3. In PowerShell, from this project folder, run these commands. Replace `YOUR-GITHUB-USERNAME` in the remote URL:

   ```powershell
   git add .
   git commit -m "Prepare Coinfolio OneNote add-in"
   git branch -M main
   git remote add origin https://github.com/YOUR-GITHUB-USERNAME/onecoin.git
   git push -u origin main
   ```

4. On GitHub, open the repository's **Settings → Pages** and set the build source to **GitHub Actions**. The workflow in `.github/workflows/pages.yml` will publish the site after the push.
5. Wait for the Pages deployment to finish. Confirm the URL `https://YOUR-GITHUB-USERNAME.github.io/onecoin/` opens.
6. In OneNote on the web, open a notebook and choose **Insert → Office Add-ins → My Add-ins → Upload My Add-in**. Select this project's `manifest.xml` from your computer.
7. Open Coinfolio from the add-ins list, add coin details, then choose **Insert into OneNote**.

GitHub Pages publishes the app files; the OneNote manifest is uploaded separately and points to the published site. If you rename the repository or username, update the URLs in `manifest.xml` and upload the updated manifest again. GitHub Pages sites are public, even when the source repository is private on an eligible plan.

## Local preview

Open `index.html` in a browser to preview the album UI. OneNote insertion requires opening the add-in through OneNote with the published manifest.
