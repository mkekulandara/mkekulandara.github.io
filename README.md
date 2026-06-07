# Madhukara Kekulandara — Personal Website

Personal academic website for Dr. Madhukara Kekulandara, Assistant Professor of Computer Science at Rhode Island College.

## 🚀 Deploying to GitHub Pages

### Option A — Simplest (root of repo)

1. Create a new GitHub repository named **`mkekulandara.github.io`**
2. Upload `index.html` to the root of that repository
3. Go to **Settings → Pages**
4. Under *Source*, select **Deploy from a branch**, branch `main`, folder `/root`
5. Your site will be live at `https://mkekulandara.github.io`

### Option B — Existing repo with `/docs` folder

1. Create a folder called `docs/` in any GitHub repository
2. Place `index.html` inside `docs/`
3. Go to **Settings → Pages**
4. Set source to branch `main`, folder `/docs`
5. Site lives at `https://mkekulandara.github.io/<repo-name>`

---

## 📁 File Structure

```
.
├── index.html    ← Single-file static site (all CSS/JS included)
└── README.md
```

All styles and scripts are embedded directly in `index.html` — no build step, no dependencies, no npm. Just upload and go.

---

## ✏️ Customizing

| What to change | Where in `index.html` |
|---|---|
| Profile photo / initials avatar | Find `.hero-card-avatar` |
| Add a real photo | Replace the `<div class="hero-card-avatar">` with `<img src="photo.jpg" ...>` |
| Contact form backend | Replace the `submitForm()` JS function with a Formspree/Netlify Forms call |
| Blog URL | Search `bitwiserefs.blogspot.com` |
| Colors | Edit `:root` CSS variables at the top |

### Adding a real contact form (optional)

Sign up at [formspree.io](https://formspree.io), get your endpoint, then replace the `submitForm()` function:

```javascript
async function submitForm() {
  const data = {
    name: document.getElementById('name').value,
    email: document.getElementById('email').value,
    subject: document.getElementById('subject').value,
    message: document.getElementById('message').value
  };
  const res = await fetch('https://formspree.io/f/YOUR_ID', {
    method: 'POST',
    headers: { 'Content-Type': 'application/json' },
    body: JSON.stringify(data)
  });
  if (res.ok) {
    document.getElementById('contactForm').style.display = 'none';
    document.getElementById('formSuccess').style.display = 'block';
  }
}
```

---

## 🔗 Links configured

- Google Scholar: https://scholar.google.com/citations?user=sRnq94YAAAAJ&hl=en
- LinkedIn: https://www.linkedin.com/in/madhukarakekulandara/
- GitHub: https://github.com/mkekulandara
- Blog: https://bitwiserefs.blogspot.com/
