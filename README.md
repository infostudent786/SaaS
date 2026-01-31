# 🏫 EduPress: Professional School Micro-SaaS Template

---

## 🏫 How to Use This Repo as a Template for Other Schools (SaaS Guide)

To launch a new school website using this template, follow these steps to avoid common errors and ensure a smooth deployment:

### 1. Create a New Repository
- On GitHub, click "Use this template" or fork this repo to create a new repo for the school (e.g., `schoolname-website`).
- Clone the new repo to your local machine.

### 2. Update School Branding & Content
- Edit `config/site.json`:
  - Change school name, tagline, logoUrl, heroImageUrl, principalImageUrl, theme colors, navigation, and integrations (formActionUrl, mapEmbedUrl).
- Edit `admin/config.yml`:
  - Update the `repo:` field to match the new repo name and owner.
  - Example:
    ```yaml
    backend:
      name: github
      repo: your-username/new-school-repo
      branch: main
    ```
- Update any content in `pages/` as needed for the new school.

### 3. Configure Vite for GitHub Pages
- In `vite.config.ts`, set the base path to the new repo name:
  ```js
  base: '/new-school-repo/',
  ```

### 4. Install Dependencies
```
npm install
```

### 5. Build the Project
```
npm run build
```

### 6. Copy Static Assets
```
mkdir -p dist/config
cp config/site.json dist/config/
```

### 7. Deploy to GitHub Pages (Manual Method)
```
cd dist
git init
git remote add origin git@github.com:your-username/new-school-repo.git
git checkout -b gh-pages
git add .
git commit -m "Deploy to GitHub Pages"
git push -f origin gh-pages
```
Then, in your GitHub repo settings, set Pages to deploy from the `gh-pages` branch (root folder).

### 8. Update CMS Access
- Ensure the `admin/config.yml` repo and branch fields are correct.
- Set up GitHub OAuth or Netlify Identity if needed for school staff.

### 9. Common Errors & Fixes
- **White screen**: Check Vite base path and that you are serving the built `dist` folder.
- **404 for config/site.json**: Copy the file manually as above.
- **404 for index.css or index.tsx**: Ensure you are deploying the `dist` folder, not the source.
- **Tailwind CDN warning**: For production, use Tailwind as a PostCSS plugin or CLI (see Tailwind docs).

---

## 🚀 Deployment Instructions for New Schools

Follow this checklist to deploy a new instance of EduPress for a client school.

### 1. Repository Setup
1. **Fork or Use Template**: Click "Use this template" or **Fork** this repository into your GitHub account or the client's account.
2. **Rename**: Go to **Settings > General** and change the repository name (e.g., `greenwood-international-school`).
3. **Clean Up**: If you are reselling, ensure the `README.md` is replaced with a user-guide for the school staff after setup.

### 2. Brand Configuration (`config/site.json`)
This is the "heart" of the school's identity. Edit this file to match the school's brand:
- **School Name & Tagline**: Update the display text.
- **Visual Identity**: Provide URLs for `logoUrl`, `heroImageUrl`, and `principalImageUrl`.
- **Theme Colors**: Change `primaryColor` (e.g., School Blue) and `secondaryColor` (e.g., School Gold) using hex codes.
- **Navigation**: Customize the links if the school needs fewer or different pages.

### 3. CMS Configuration (`admin/config.yml`)
To allow school staff to edit content via the `/admin` dashboard:
1. Open `admin/config.yml`.
2. **Crucial**: Update the `repo` field to match your new repository path:
   ```yaml
   backend:
     name: github
     repo: your-username/your-new-repo-name
     branch: main
   ```
3. **OAuth Setup**: Configure GitHub OAuth (via Netlify Identity or a proxy) so the school staff can log in using their own credentials.

### 4. Functional Integrations
*A static site needs external "engines" for dynamic data.*
- **Forms (Contact & Admissions)**: 
  - Create an account at [Formspree.io](https://formspree.io/).
  - Create a new form and copy the "Endpoint URL".
  - Paste this into the `formActionUrl` field in `site.json`.
- **Google Maps**:
  - Find the school on Google Maps.
  - Click **Share > Embed a map**.
  - Copy ONLY the URL inside the `src` attribute and paste it into the `mapEmbedUrl` in `site.json`.

### 5. Hosting (GitHub Pages)
1. Go to **Settings > Pages** in your GitHub repository.
2. Under **Build and deployment > Source**, select "Deploy from a branch".
3. Select the `main` branch and the `/(root)` folder.
4. Click **Save**. Within minutes, the site will be live at `https://your-username.github.io/repo-name/`.

---

## 🤝 Reselling & Handover Guide

When selling this template as a service, follow these best practices for a smooth handover:

### Client Deliverables
- **Live URL**: Provide the GitHub Pages link or a custom domain (e.g., `www.schoolname.edu`).
- **Admin Access**: Provide instructions on how to log in at `yourdomain.com/admin`.
- **Staff Training**: Give them a 15-minute walkthrough of the CMS:
  - How to post a new **Notice**.
  - How to upload **Exam Results** (PDFs).
  - How to update the **Gallery**.

### Custom Domains
If the school has its own domain:
1. Go to **Settings > Pages** and enter the domain in the "Custom domain" field.
2. Configure the school's DNS provider (A records pointing to GitHub IPs and CNAME for `www`).
3. GitHub provides **Free SSL** automatically once the DNS is verified.

---

## 💰 The Micro-SaaS Business Model

1. **One-Time Setup Fee ($300 - $1,500)**: Cover your time for branding, SEO setup, and initial data entry.
2. **Annual Maintenance ($150 - $400)**: Charge for domain renewal, priority support, and periodic content backups.
3. **Pure Profit**: Since your hosting cost is $0, every dollar earned after the initial work is pure profit.

---

====================================================
🛠️ Deployment & Troubleshooting Steps (2026)
0. Prerequisites
Install Node.js & npm: Download from https://nodejs.org/ and install. Verify with node -v and npm -v.
1. Install Dependencies
  npm install
2. Vite Configuration for GitHub Pages
base: '/SaaS/',
This ensures correct asset loading on GitHub Pages.
3. SSH Setup (Optional)
Change your git remote to SSH
git remote set-url origin git@github.com:infostudent786/SaaS.git
4. Build the Project
npm run build
5. Copy Static Assets
Manually copy site.json to site.json after each build:

mkdir -p dist/config
cp config/site.json dist/config/
6. Deploy to GitHub Pages (Manual Method)
cd dist
git init
git remote add origin git@github.com:infostudent786/SaaS.git
git checkout -b gh-pages
git add .
git commit -m "Deploy to GitHub Pages"
git push -f origin gh-pages

7. Common Issues & Fixes
White Screen: Usually caused by missing base path or not serving built files.
404 for config/site.json: Copy the file manually as above.
404 for index.css or index.tsx: Ensure you are deploying the dist folder, not the source.
Tailwind CDN Warning: For production, use Tailwind as a PostCSS plugin or CLI (see Tailwind docs).
===============================================

*Need technical assistance or custom feature development for a client? Reach out via our developer support channel.*