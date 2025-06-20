# Treegaze Mirror

This repository automatically mirrors and deploys the [ngit-repo-explorer](https://relay.ngit.dev/npub1hw6amg8p24ne08c9gdq8hhpqx0t0pwanpae9z25crn7m9uy7yarse465gr/ngit-repo-explorer.git) project to GitHub Pages.

## How it works

The GitHub Action (`.github/workflows/deploy.yml`) runs every 10 minutes and:

1. Checks the latest commit from the external repository
2. Compares it with the last known commit hash
3. If there are changes (or if manually triggered), it:
   - Clones the external repository
   - Copies the content to this repository
   - Runs `npm run build`
   - Deploys the `dist` folder to GitHub Pages
   - Stores the new commit hash for future comparison

## Manual Deployment

You can manually trigger a deployment by going to the Actions tab and running the "Monitor External Repo and Deploy" workflow.

## Setup Requirements

To use this in your own repository:

1. Enable GitHub Pages in your repository settings
2. Set the Pages source to "GitHub Actions"
3. The workflow will handle the rest automatically

## External Repository

- Source: https://relay.ngit.dev/npub1hw6amg8p24ne08c9gdq8hhpqx0t0pwanpae9z25crn7m9uy7yarse465gr/ngit-repo-explorer.git
- Monitoring: Main branch
- Check frequency: Every 10 minutes