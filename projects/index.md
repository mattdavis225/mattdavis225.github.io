---
layout: default
title: Guide to E-Portfolio Creation (Milestone 1)
---

# Guide to E-Portfolio Creation (Milestone 1)

## Introduction
This tutorial provides a comprehensive guide on how I created my professional e-portfolio using GitHub Pages for Milestone 1 of my class assignment. The e-portfolio showcases my professional skills, education, and work experience, built using the Jekyll Minimal theme for its clean and simple design. This guide is intended for newcomers, detailing every step from setting up a GitHub repository to customizing the portfolio’s appearance and content. It includes references to resources used, screenshots of key stages, and tips for using tools like Visual Studio Code (VSCode) to streamline the process.

## Step-by-Step Guide
Below are the detailed steps I followed to create my e-portfolio, organized into sections for clarity.

### Step 1: Setting Up GitHub Pages
GitHub Pages provides a free platform to host static websites directly from a GitHub repository. Here’s how I set it up:

1. **Create a GitHub Account:** If you don’t already have one, sign up at [GitHub](https://github.com).
2. **Create a Repository:** I created a public repository named `mattdavis225.github.io`, where `mattdavis225` is my GitHub username. This naming convention automatically enables GitHub Pages for the repository.
   - Navigate to GitHub, click the “+” icon, and select “New repository.”
   - Name it `<your-username>.github.io` and set it to public.
   - Initialize it with a README file for basic setup.
3. **Enable GitHub Pages:** In the repository settings, under the “Pages” tab, I ensured the source was set to the main branch and the root folder (/), which hosts the site at `https://<your-username>.github.io`.

**Resource:** [GitHub Pages documentation](https://docs.github.com/en/pages)

### Step 2: Selecting and Downloading the Jekyll Minimal Theme
I chose the Jekyll Minimal theme for its simplicity, which allowed me to focus on content rather than complex design.

1. **Download the Theme:** I visited the [Jekyll Minimal theme repository](https://github.com/pages-themes/minimal).
   - Clicked the green “Code” button and selected “Download ZIP.”
   - Extracted the ZIP file to my local machine (e.g., `Desktop/OneDrive/mattdavis225.github.io`).
2. **Understand the Theme Structure:** The downloaded folder contained key files like:
   - `_config.yml`: Configuration file for site-wide settings.
   - `index.md`: The main page content in Markdown.
   - `_sass/minimal.scss`: Stylesheet for customizing the theme’s appearance.
   - `assets/img/`: Directory for storing images like logos or screenshots.

**Resource:** [Jekyll Minimal Theme Repository](https://github.com/pages-themes/minimal)

### Step 3: Cloning the Repository
To work on the portfolio locally, I cloned my GitHub repository to my computer using Visual Studio Code (VSCode).

1. **Install VSCode:** I downloaded and installed VSCode from [VSCode](https://code.visualstudio.com).
2. **Clone the Repository:**
   ```bash
   git clone https://github.com/mattdavis225/mattdavis225.github.io.git
   cd Desktop/OneDrive/mattdavis225.github.io
   ```
3. **Copy Theme Files:** I copied the contents of the extracted Jekyll Minimal theme folder into the cloned repository folder, overwriting any default files (e.g., `index.md`, `_config.yml`).
4. **Initial Commit:**
   ```bash
   git status
   git add .
   git commit -m "Initial commit with Jekyll Minimal theme"
   git push origin main
   ```

**Resource:** [Git documentation](https://git-scm.com/doc)

### Step 4: Configuring the Theme
I customized the e-portfolio by editing key files to reflect my personal and professional details.

#### Updating _config.yml
The `_config.yml` file controls site-wide settings. I updated it to include my details:

```yaml
title: Matthew Davis Online Portfolio
logo: /assets/img/logo.jpg
description: Dynamic Supply Chain and Logistics professional with expertise in...
theme: jekyll-theme-minimal
```

**Add Logo Image:**
- Selected a professional headshot and renamed it to `logo.jpg`.
- Created an `assets/img/` folder in the repository (if it didn’t exist).
- Copied `logo.jpg` into `assets/img/`.

**Preview Changes:** I used VSCode’s Markdown Preview feature to view how the updated `_config.yml` affected the site’s header.  
- In VSCode, right-click `index.md` and select “Open Preview” or press `Ctrl+Shift+V`.

**Resource:** [VSCode Markdown Preview documentation](https://code.visualstudio.com/docs/languages/markdown#_markdown-preview)

#### Customizing Styles
To personalize the theme’s appearance, I modified the SCSS files:

```scss
font-family: "Arial", sans-serif;
a { color: #2a7ae2; }
```

Although I didn’t run a local Jekyll server, I pushed changes to GitHub to preview them live at [https://mattdavis225.github.io](https://mattdavis225.github.io).

### Step 5: Creating Content for the Main Page
The `index.md` file in the root folder hosts the main page content. I structured it to mirror my professional resume.

```markdown
# Matthew Davis

## Skills
- Supply Chain Optimization
- Logistics Management
- Data Analysis with Excel and Python

## Education
- Bachelor of Science in Supply Chain Management, [University Name], [Year]

## Work Experience
- **Logistics Coordinator**, [Company Name], [Year–Year]
  - Managed end-to-end supply chain operations...
```

**Resource:** [Markdown Guide](https://www.markdownguide.org/cheat-sheet)

### Step 6: Finalizing and Publishing
After completing the content and styling, I finalized the portfolio and published it.

```bash
git add .
git commit -m "Completed Milestone 1: Added portfolio content and customizations"
git push origin main
```

Then, I verified the live site at [https://mattdavis225.github.io](https://mattdavis225.github.io).

## Screenshots of the Process
- **Theme Customization:** Editing `_sass/minimal.scss` to change link colors in VSCode.  
- **Final Live Page:** The completed e-portfolio as it appears online.  
- **Live URL Confirmation:** Browser address bar showing the correct URL for my GitHub Pages site.

## Resources Used
- [Jekyll Minimal Theme](https://github.com/pages-themes/minimal)
- [GitHub Pages Documentation](https://docs.github.com/en/pages)
- [VSCode Markdown Preview](https://code.visualstudio.com/docs/languages/markdown#_markdown-preview)
- Markdown Cheatsheet (Provided by my professor, screenshot: `../assets/img/markdown_cheatsheet.png`)
- [Git Documentation](https://git-scm.com/doc)

## Conclusion
By following these steps, I successfully created a professional e-portfolio hosted on GitHub Pages using the Jekyll Minimal theme. The process involved setting up a repository, cloning it locally, customizing the theme, adding content, and publishing the site. Using VSCode’s Markdown Preview and Git commands streamlined the workflow, making it accessible even for beginners. This guide should help anyone replicate the process to create their own e-portfolio.