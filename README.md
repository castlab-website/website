# Website Repository Documentation

This repository contains the source code and configuration files for the laboratory website. The site is built utilizing **Astro** as the core web framework, chosen specifically for its high performance in delivering static, content-heavy websites. 

## Packages Required / Setup Steps
1) Install Node.js and the npm package manager
2) Clone the repo 
3) Cd into repo and run "npm install". This downloads all the dependencies listed in package.json
4) To run the website locally, use "npm run dev". Note: that if you run into Node.js version issue telling you to upgrade, running "nvm use —lts" and then "npm run rev" may help.

## Deployment & Hosting
The website is published and hosted via **GitHub Pages**. Deployment is fully automated through GitHub Actions. 
* Pushing changes to the main branch of the repository automatically triggers a new build and deployment.
* Deployment status can be monitored directly in the GitHub repository next to the commit message (a green checkmark indicates success, while a red 'X' indicates failure; clicking the icon provides detailed logs).
* `astro.config.mjs` and the `.github/workflows/` directory contain all necessary configurations to link the Astro build process with GitHub Pages.

## Directory Structure

### Root Directory
* **`.json` files:** Auto-generated configuration files created by Astro. These generally do not require manual modification.
* **`Organizational Files` folder:** Contain initial design visions, mockups for the website, markdown files generated during inital development and brainstorming.
* **`.DS_Store`:** System-generated macOS files. These are unnecessary and can be safely ignored or removed during repository cleanup.

### `/public`
* **`/public/img/`:** The primary image directory holding all active images used across the website. 

### `/src`
The core directory containing all site source code, structured data, and assets used by Astro to render the site. Naming conventions are designed to be self-explanatory.

* **`/src/components/`**
  * Houses reusable UI elements.
  * Contains the global `Header` and `Footer` components used across all pages.
  * Contains `MemberCard` and `ProjectCard`, which serve as reusable templates for the "People" and "Research" pages.

* **`/src/layouts/`**
  * Contains `MainLayout`, the primary page wrapper that handles the global HTML structure and layout for the entire site.

* **`/src/pages/`**
  * The primary working directory where most content editing occurs.
  * `index.astro`: The website's homepage.
  * `people.astro`: The directory page for lab members.
  * `publications.astro`: The list of laboratory publications.
  * **`/src/pages/research/`**:
    * `index.astro`: The main research overview page.
    * `[project].astro`: Dynamic routing for individual project pages. 

## Content Management Guide

The site utilizes localized data structures to populate its pages. To update the website content, locate the respective files in the `/src/pages/` directory and modify the corresponding data constants.

**Adding New Team Members**
1. Navigate to `src/pages/people.astro`.
2. Locate the `teamMembers` constant.
3. Insert a new entry following the existing format, providing the `name`, `title`, `bio`, and `imagesrc`.

**Adding New Publications**
1. Navigate to `src/pages/publications.astro`.
2. Locate the `publications` constant under the appropriate year.
3. Insert a new entry following the established format, including the `title`, `authors`, `journal`, and any relevant `links`.

**Adding New Research Projects**
1. Research projects utilize a localized database for storing project information and text.
2. Add a new entry to the database for the new project.
3. Ensure the project naming convention in the new entry exactly matches the routing between the relevant `.astro` files to ensure pages render correctly.

## Useful Tips For Development
1. When developing locally with "npm run dev", it times out without you noticing. If pages aren't loading properly or changes made aren't being reflected, restarting your host.

## To Do
1. Downsampling homepage image for less pixels so that it renders quicker
2. Add in another tab for bcdc affiliations etc.
3. Edit contact info in footer and people's page
4. Edit publications page
5. Edit homepage to match information from rest of website