# Jekyll + Minimal Mistakes + Decap CMS

Blog Jekyll con tema Minimal Mistakes e pannello admin Decap CMS.
Hosting su Cloudflare Pages — 100% gratis, senza limiti.

## 🚀 Deploy in 1 click su Cloudflare Pages

1. Vai su **pages.cloudflare.com** → login con GitHub
2. Clicca **"Create a project"** → **"Connect to Git"**
3. Scegli il repo **Jekyllpanel**
4. Imposta build settings:
   - Framework preset: **Jekyll**
   - Build command: `jekyll build`
   - Build output directory: `_site`
5. Clicca **"Save and Deploy"** ✅

## 🔐 Attivare il pannello admin

Dopo il deploy, il login admin usa **GitHub OAuth**:

1. Vai su **github.com/settings/developers**
2. Clicca **"New OAuth App"**
3. Compila:
   - Homepage URL: `https://tuosito.pages.dev`
   - Callback URL: `https://tuosito.pages.dev/admin`
4. Copia **Client ID** e **Client Secret**
5. Vai su `/admin` → accedi con GitHub ✅

## Struttura

```
├── _posts/          # Articoli blog
├── admin/           # Pannello Decap CMS
├── assets/images/   # Immagini
├── _config.yml      # Configurazione Jekyll
└── about.md         # Pagina Chi Sono
```
