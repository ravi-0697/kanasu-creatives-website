# Kanasu Creatives — Vue 3 Website

A responsive Vue 3 + Vite photography and videography landing page for Kanasu Creatives.

## Run locally

Requirements: Node.js 20.19+ or 22.12+ recommended.

```bash
npm install
npm run dev
```

Open the local URL printed by Vite (usually http://localhost:5173).

## Create a production build

```bash
npm run build
```

The deployable static website is generated in `dist/`.

## Deploy to Azure Static Web Apps

Recommended route: GitHub-connected deployment.

1. Create a GitHub repository and upload these project files.
2. In Azure Portal, search for **Static Web Apps** and choose **Create**.
3. Choose your subscription, resource group, a unique app name, and the Free plan if it fits your needs.
4. Select GitHub as the deployment source and authorise the repository.
5. Build preset: **Vue** (or Custom if the portal does not offer Vue).
6. App location: `/`
7. API location: leave blank
8. Output location: `dist`
9. Create the resource and wait for the GitHub Actions deployment to finish.
10. Open the Azure-generated URL and test it.
11. In the Static Web App resource, open **Custom domains** and add `kanasucreatives.com`. Follow the DNS validation and record instructions Azure displays.
12. If you also want `www.kanasucreatives.com`, add it as another custom domain and configure its DNS as Azure instructs.

## Domain and Google Workspace email

Your website's DNS records and Google Workspace mail records can coexist. Do **not** delete or overwrite Google Workspace MX records or other mail-related records when adding Azure's website records. Add only the records Azure requests for the custom domain. If your DNS is managed by Squarespace Domains or another registrar, make changes in that provider's DNS settings.

## Before publishing

- Replace the sample gallery images in `src/App.vue` with images you own or have permission to use.
- Confirm the WhatsApp phone number in `src/App.vue` (`917411544639`) is the correct business number, including country code, with no `+` or spaces in the URL.
- Confirm the service area and email address.
- Add your own privacy policy if you later collect enquiry form details or analytics.
- The current contact actions use email and WhatsApp links; no backend or form storage is configured.
