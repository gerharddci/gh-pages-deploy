# Step-by-Step Guide: Deploying a Website on Render

In this guide, you'll learn how to host a static website on [Render.com](https://render.com/) with ease.

---

### 1. Visit Render.com and Sign Up

1. Go to [https://render.com/](https://render.com/) and click **Sign Up**.
2. You can sign up using your GitHub, GitLab, or Google account. Choose the one that's linked to your project.

---

### 2. Create a New Web Service

1. Once logged in, click on the **New** button at the top, then select **Static Site**.

---

### 3. Connect Your GitHub or GitLab Account

1. Render will prompt you to connect your GitHub or GitLab account.
2. Authorize Render to access your repositories.

---

### 4. Select Your Repository

1. After connecting, you'll see a list of your repositories.
2. Select the repository that contains the site you want to deploy.

---

### 5. Configure the Deployment

1. **Name**: Give your site a name.
2. **Branch**: Choose the branch you want to deploy (usually `main` or `master`).
3. **Build Command** (if needed): If you're using a static site generator or framework (e.g., React, Gatsby), enter the build command like `npm run build`.
4. **Publish Directory**: For React or similar, use `build/` as the directory (the folder where the site will be served from after it's built).

---

### 6. Deploy Your Site

Once you've filled in the configuration details, click **Create Static Site**.

Render will automatically build and deploy your site.

---

### 7. View Your Deployed Site

Once the deployment is complete, Render will provide a live URL where your site is hosted. You can share this URL and visit your live site anytime.

---

### Learn More About Render

For more information, visit [Render's documentation](https://render.com/docs).