# IBM SkillsBuild Prototype — Setup Guide (for total beginners)

This is a working React prototype: 4-step onboarding (create account → goal →
current role/resume → time commitment) plus a Career Experience Simulator.

## What these tools are, quickly

- **VSCode** = the text editor you'll write/view code in.
- **Node.js** = lets your computer actually run JavaScript projects like this one.
- **Git** = tracks changes to your code over time.
- **GitHub** = an online place to store your code (like Google Drive, but for code).

## Step 1 — Install the tools (one-time setup)

1. Install **Node.js**: go to https://nodejs.org and download the "LTS" version. Run the installer, click through with defaults.
2. Install **VSCode**: https://code.visualstudio.com — download and install for your OS.
3. Install **Git**: https://git-scm.com/downloads — download and install (defaults are fine).
4. Create a **GitHub account** at https://github.com if you don't have one.

To check everything installed correctly, open a terminal (on Mac: Terminal app; on Windows: search "Command Prompt") and type:
```
node -v
git --version
```
Both should print a version number.

## Step 2 — Open this project in VSCode

1. Unzip the folder you downloaded from me.
2. Open **VSCode**.
3. Go to **File → Open Folder** and select the unzipped `skillpath` folder.
4. In VSCode, open the built-in terminal: **Terminal → New Terminal** (top menu).

## Step 3 — Install dependencies and run it

In that VSCode terminal, type:
```
npm install
```
This downloads all the packages the project needs (takes a minute). Then run:
```
npm run dev
```
It'll print a local address like `http://localhost:5173`. Open that in your browser — your site is now running on your own computer.

Every time you save a file in VSCode, the browser will auto-refresh.

## Step 4 — Push it to GitHub (so it's backed up and shareable)

1. On github.com, click the **+** icon (top right) → **New repository**. Name it `skillpath-prototype`, leave it Public or Private, don't add a README (you already have one), click **Create repository**.
2. GitHub will show you a page with commands. Back in your VSCode terminal, type these one at a time (replace `YOUR-USERNAME` with your actual GitHub username):

```
git init
git add .
git commit -m "first version of skillpath prototype"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/skillpath-prototype.git
git push -u origin main
```

3. Refresh your GitHub repo page — your code is now online.

From now on, whenever you make changes and want to save them to GitHub, just run:
```
git add .
git commit -m "describe what you changed"
git push
```

## Project structure

```
skillpath/
  src/
    pages/
      Home.jsx              → runs the 4-step onboarding wizard
      onboarding/            → one file per step (Step1–Step4) + summary screen
      CareerSimulator.jsx    → the "try a career" feature
      HomeDashboard.jsx      → the "logged in" homepage showing courses
      Profile.jsx
    components/
      Navbar.jsx             → top nav, includes the Career Simulator tab
    context/
      OnboardingContext.jsx  → stores answers so every page can read them
```

## Editing tips

- To change onboarding questions: open `src/pages/onboarding/StepX*.jsx`.
- To add more sample careers to the simulator: open `src/pages/CareerSimulator.jsx` and edit the `CAREERS` array near the top — copy one of the existing objects and change the values.
- Colors/fonts are defined once in `tailwind.config.js` under `theme.extend`.
