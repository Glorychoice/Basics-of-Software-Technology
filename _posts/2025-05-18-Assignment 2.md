---
title: "Assignment 2"
date: 2025-04-24
---

# My Report 
**Here is the Documentation of the entire process of setting up and deploying the website**
**Step 1: Initialize Project**
- Commit: Initialize Vite + React project with npm
  
**Step 2: Project Structure and Initial Page Design**
- Created basic components (Navbar, Home, Footer).
- Setup folder structure: /components, /assets, /pages.
- Commit: Setup project structure and base UI components
  
**Step 3: Add Routing (React Router)**
- Implemented navigation between pages (Home, About, Contact).
- Commit: Implement basic routing with React Router

**Step 4: Styling with TailwindCSS**
- Tailwind enables rapid styling using utility-first classes.
- Commit: Integrate TailwindCSS for styling

**Step 5: Add Content and Assets**
- Added images, dummy content, and interactive UI elements.
- Commit: Add content and visual assets
  
**Step 6: Build and Test Locally**
- Tested responsiveness and accessibility.
- Commit: Test local build and ensure responsiveness
  
## Deployment Process
# Prepare for Deployment to GitHub Pages
- Add the following to vite.config.js
- Update package.json
- Commit: Configure Vite for GitHub Pages deployment

# Push to GitHub
- Commit: Initial push to GitHub repository

# Deploy using GitHub Actions
- Added deploy.yml in .github/workflows to automate deployment.
- Used peaceiris/actions-gh-pages for deployment from dist/ directory.
- Commit: Add GitHub Actions workflow for auto-deployment

# Git Management Strategy
# Commit Message	                                         Purpose
Initialize project                                       Base project setup
Setup components and pages	                             Establish foundational UI
Implement routing	                                       Add navigation
Add TailwindCSS                                          Improve UI styling
Add content/assets	                                     Fill with content
Test build	                                             Ensure site works locally
Configure deployment	                                   Ready for GitHub Pages
Push to GitHub	                                         Source control
Add CI/CD	                                               Enable automatic deployment

- Branch Strategy: Feature branches for major changes, merged via pull requests into main.

## The choice of tools or frameworks used for the static site.
# Choice of Tools and Frameworks
**1. Vite (with React)**
Why Vite?

Vite is a modern build tool that offers blazing-fast development startup and hot module replacement.

It’s optimized for modern JavaScript frameworks like React and provides a smoother developer experience than older tools like Webpack.

Why React?

React allows building UI using reusable components, which makes the development modular and maintainable.

Even though the site is static, React adds flexibility for interactivity (e.g., navigation, animations, dynamic content without backend).

**2. TailwindCSS**
Why TailwindCSS?

TailwindCSS is a utility-first CSS framework that speeds up styling without writing custom CSS.

It encourages consistency and responsiveness across devices and greatly reduces the need for external stylesheets.

**3. Git + GitHub**
Why Git?

Git is a version control system that tracks changes, supports collaboration, and allows reverting to previous versions if needed.

Why GitHub?

GitHub acts as a remote repository and also integrates seamlessly with GitHub Pages for free static hosting.

**4. GitHub Pages**
Why GitHub Pages?

It’s a free hosting service for static sites that directly connects with GitHub repositories.

Supports CI/CD via GitHub Actions, enabling automatic deployment whenever changes are pushed to the repo.

**5. React Router (Optional if Multi-Page)**
Why React Router?

For a multi-page feel in a Single Page Application (SPA), React Router allows smooth client-side routing.

Improves navigation experience without full page reloads.

## Conclusion
This project demonstrates the full lifecycle of developing and deploying a modern static website using Vite + React. Git and GitHub streamlined collaboration and version control, while GitHub Pages offered a seamless deployment experience.
