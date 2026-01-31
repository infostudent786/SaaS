# 🏫 EduPress: Professional School Micro-SaaS Template

EduPress is a high-performance school website template designed for rapid white-labeling and mass-deployment. Built with React and Tailwind, it allows you to launch professional school websites in minutes with **Zero Hosting Costs** via GitHub Pages.

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

*Need technical assistance or custom feature development for a client? Reach out via our developer support channel.*