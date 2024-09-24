# Step-by-Step Guide: Deploying a React App on GitHub Pages

In this guide, we'll walk you through how to deploy your React app on GitHub Pages, so it becomes accessible online!

### 1. Navigate to Your React App Folder

First, make sure you're working inside the folder where your React app is located. To do this, use the terminal/command prompt:

```bash
$ cd {path-to-your-project}
```

Replace `{path-to-your-project}` with the actual path to your project folder.

---

### 2. Install `gh-pages`

To deploy to GitHub Pages, we need a package called `gh-pages`. Let's install it as a development dependency:

```bash
$ npm install gh-pages --save-dev
```

This will allow us to automate the deployment process.

---

### 3. Set the `homepage` in Your `package.json`

We need to tell GitHub where to find your site. Open the `package.json` file (located in your project folder), and add a `homepage` property like this:

```json
"homepage": "https://{your-github-username}.github.io/{your-repo-name}"
```

- Replace `{your-github-username}` with your GitHub username.
- Replace `{your-repo-name}` with the name of your GitHub repository.

Example:

```json
"homepage": "https://johndoe.github.io/my-awesome-app"
```

---

### 4. Add Deployment Scripts to `package.json`

Now, we need to tell npm how to build and deploy the project. In the `package.json` file, find the `"scripts"` section and add two new commands:

```json
"scripts": {
  "predeploy": "npm run build",
  "deploy": "gh-pages -d dist",
  "start": "vite",
  "build": "vite build",
}
```

- `"predeploy"` will build your app before deployment.
- `"deploy"` will upload the `dist` folder to GitHub Pages. Sometimes this can also be called the `build` folder.

---

### 5. Push Your React App to GitHub

Before we can deploy, make sure your project is pushed to GitHub. If you haven't done this already, follow these steps:

1. Initialize Git (if you haven't already):

   ```bash
   $ git init
   ```

2. Add a remote pointing to your GitHub repository:

   ```bash
   $ git remote add origin https://github.com/{your-github-username}/{your-repo-name}.git
   ```

3. Add all your files and commit them:

   ```bash
   $ git add .
   $ git commit -m "Initial commit"
   ```

4. Push the code to GitHub:

   ```bash
   $ git branch -M main
   $ git push origin main
   ```

---

#### For vite add

Add the following to your vite.config.js

```js
export default defineConfig({
  plugins: [react()],
  base: "/{repo-name}/", // Replace {repo-name} with your repository name
});
```

---

### 6. Deploy Your App

Now, we can deploy the app. Run the following command:

```bash
$ npm run deploy
```

- This will first build your app (`predeploy`).
- Then it will upload the build folder to a new branch called `gh-pages` on your GitHub repository.

---

### 7. Configure GitHub Pages

Finally, we need to tell GitHub where to find your site.

1. Go to your GitHub repository on the website.
2. Click the **Settings** tab.
3. In the sidebar, under "Code and Automation," click **Pages**.
4. In the "Build and Deployment" section:
   - **Source**: Select "Deploy from a branch"
   - **Branch**: Select `gh-pages`
   - **Folder**: Leave it as `/ (root)`
5. Click **Save**.

---

### 8. View Your Live App!

After a few minutes, your app will be live! You can access it at:

```
https://{your-github-username}.github.io/{your-repo-name}
```

If it doesn't show up right away, wait a minute and refresh the page.

That's it! You've successfully deployed your React app to GitHub Pages. 🎉