# atomiqs.ai — Website

One-pager website for [atomiqs.ai](https://atomiqs.ai), hosted via GitHub Pages.

## Deployment (GitHub Pages — HTTPS)

### Quick setup

1. **Create a new GitHub repository** named `atomiqs-website` (or any name you prefer).

2. **Upload these files** to the root of the repository:
   - `index.html`
   - `README.md` (optional)
   - `_config.yml` (optional, for Jekyll config)

3. **Enable GitHub Pages**:
   - Go to your repository → **Settings** → **Pages**
   - Under *Source*, select **Deploy from a branch**
   - Set branch to `main` (or `master`) and folder to `/ (root)`
   - Click **Save**

4. **Your site goes live** at:
   `https://YOUR-GITHUB-USERNAME.github.io/atomiqs-website/`

   GitHub Pages serves all sites over **HTTPS automatically** — no extra config needed.

---

### Custom domain (atomiqs.ai)

To serve the site at `https://atomiqs.ai`:

1. **Add a `CNAME` file** to the repo root containing:
   ```
   atomiqs.ai
   ```

2. **Update your DNS** (at your domain registrar / Cloudflare / etc.):

   | Type  | Name            | Value                                      |
   |-------|-----------------|--------------------------------------------|
   | A     | @               | 185.199.108.153                            |
   | A     | @               | 185.199.109.153                            |
   | A     | @               | 185.199.110.153                            |
   | A     | @               | 185.199.111.153                            |
   | CNAME | www             | YOUR-GITHUB-USERNAME.github.io             |

3. **In GitHub Pages settings**, enter `atomiqs.ai` under *Custom domain* and check **Enforce HTTPS**.

   DNS propagation takes 5–60 minutes. GitHub will automatically provision a free TLS certificate via Let's Encrypt.

---

### Contact form (email submissions)

The form is wired up and ready — you just need to connect an email endpoint. Two free options:

#### Option A — Formspree (recommended, 50 free submissions/month)
1. Sign up at [formspree.io](https://formspree.io)
2. Create a new form → set the destination email to **admin@myvyoma.io**
3. Copy your form ID (e.g. `xabcdefg`) from the dashboard
4. Open `index.html`, find `YOUR_FORM_ID` and replace it with your actual ID
5. Save and push — submissions will arrive at **admin@myvyoma.io** immediately

#### Option B — EmailJS (free tier)
1. Sign up at [emailjs.com](https://www.emailjs.com)
2. Create a service + template
3. Replace the three IDs in the commented block in `index.html`

---

### Local preview

Open `index.html` directly in any browser — no build step required.

Or use a local server:
```bash
npx serve .
# then open http://localhost:3000
```
