# Portfolio Website

A modern, responsive portfolio website built with React, TypeScript, Vite, and Tailwind CSS. This project showcases your skills, projects, and professional background in a clean and interactive interface.

## 🚀 Getting Started

Follow these steps to set up the project on your local machine.

### Prerequisites

Make sure you have **Node.js** installed. You can download it from [nodejs.org](https://nodejs.org/).

### Installation

1.  **Clone the repository** (if you haven't already):

    ```bash
    git clone <repository-url>
    cd lavidata-main
    ```

2.  **Install dependencies**:

    ```bash
    npm install
    ```

3.  **Start the development server**:

    ```bash
    npm run dev
    ```

4.  **Open in your browser**:
    The terminal will show a local URL (usually `http://localhost:5173`). Open this link to view your website.

---

## 🛠️ Customization Guide

This guide explains how to update the content of your portfolio. All the main content is located in the `src/components` folder.

### 1. Personal Information (Hero Section)

To change your **Name**, **Title**, **Bio**, or **Social Media Links**:

- Open `src/components/Hero.tsx`.
- Look for the text inside the HTML tags (e.g., `<h1>`, `<p>`).
- Update the links in the `href` attributes for GitHub, LinkedIn, and Email.

### 2. About Me

To update your **About** description:

- Open `src/components/About.tsx`.
- Modify the text inside the `<p>` tags to reflect your background and journey.

### 3. Skills

To add or remove **Skills**:

- Open `src/components/Skills.tsx`.
- Locate the `skillCategories` array at the top of the file.
- You can add new categories or edit the `skills` list within each category.
  ```javascript
  {
    icon: Code2,
    title: "Programming Languages",
    skills: ["Python", "C/C++", "SQL", "JavaScript"] // Add or remove items here
  },
  ```

### 4. Projects

To update your **Projects**:

- Open `src/components/Projects.tsx`.
- Locate the `projects` array at the top of the file.
- Each project is an object where you can change the `title`, `description`, `tags`, `github` link, and `demo` link.
  ```javascript
  {
    title: "Your Project Title",
    description: "Brief description of what you built.",
    tags: ["Tech 1", "Tech 2"],
    github: "https://github.com/yourusername/project",
    demo: "https://your-demo-link.com"
  }
  ```

### 5. Contact Information

To update your **Email**, **Phone**, or **Location**:

- Open `src/components/Contact.tsx`.
- Locate the `contactInfo` array at the top of the file.
- Update the `value` and `href` fields.

### 6. Resume

To update your **Resume/CV**:

- Place your new PDF file in the `public` folder.
- Rename it to `resume.pdf` (or update the filename in `src/components/Hero.tsx` line 8).

### 7. Images

- Place new images in the `src/assets` folder.
- Import them in the component where you want to use them:
  ```javascript
  import myImage from "@/assets/my-image.jpg";
  ```
- Use the imported variable in the `src` attribute of an `<img>` tag.

### 8. Navigation Bar & Footer

To update your **Name** or **Social Links** in the header and footer:

- **Navbar**: Open `src/components/Navbar.tsx` and find the text inside the `<a>` tag (around line 78).
- **Footer**: Open `src/components/Footer.tsx` and update the name, description, and social links.

---

## 📦 Deployment

The easiest way to deploy this website is using **Vercel** or **Netlify**.

1.  Push your code to a GitHub repository.
2.  Log in to Vercel or Netlify.
3.  Import your repository.
4.  The platform will automatically detect the settings (Vite framework).
5.  Click **Deploy**.

Your website will be live in minutes!

### Option 2: GitHub Pages (Free Hosting)

If you prefer to host it directly on GitHub, follow these steps:

1.  **Install the `gh-pages` package**:
    Open your terminal and run:

    ```bash
    npm install gh-pages --save-dev
    ```

2.  **Update `package.json`**:
    Open the `package.json` file and add the following lines.

    At the top level (e.g., under `"name"`), add your homepage URL:

    ```json
    "homepage": "https://<your-github-username>.github.io/<repository-name>",
    ```

    _(Replace `<your-github-username>` and `<repository-name>` with your actual details)_

    In the `"scripts"` section, add these two lines:

    ```json
    "predeploy": "npm run build",
    "deploy": "gh-pages -d dist"
    ```

3.  **Update `vite.config.ts`**:
    Open `vite.config.ts` and add the `base` property inside `defineConfig`. It should look like this:

    ```typescript
    export default defineConfig(({ mode }) => ({
      base: "/<repository-name>/", // Add this line!
      server: {
        // ... existing code
    ```

    _(Make sure to replace `<repository-name>` with the name of your GitHub repo, e.g., `/my-portfolio/`)_

4.  **Deploy**:
    Run the following command in your terminal:

    ```bash
    npm run deploy
    ```

5.  **Configure GitHub Settings**:
    - Go to your repository on GitHub.
    - Click on **Settings** > **Pages**.
    - Under **Source**, ensure it is set to **Deploy from a branch**.
    - Select the **gh-pages** branch and click **Save**.

Your site should now be live at your homepage URL!

### Option 3: Manual Deployment (If Option 2 fails)

If `npm run deploy` fails (common on Windows), use these manual steps:

1.  **Build the project**:

    ```bash
    npm run build
    ```

2.  **Deploy manually**:
    Run these commands one by one in your terminal:
    ```bash
    cd dist
    git init
    git add -A
    git commit -m "deploy"
    git push -f https://github.com/<your-username>/<repository-name>.git master:gh-pages
    ```
    _(Replace `<your-username>` and `<repository-name>` with your actual details)_

---

## 📂 Project Structure

- `src/components`: Contains all the UI sections (Hero, About, Projects, etc.).
- `src/assets`: Stores images and static assets.
- `src/App.tsx`: The main entry point that assembles the page.
- `public`: Static files like `resume.pdf` and `favicon`.
