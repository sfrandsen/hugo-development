Spring over, og gå til indhold
Du sagde:
i need a template for a hugo site, it should resemble medium.com to start with, then i can adjust it
ChatGPT sagde:
A good way to get a Medium-like starting point in Hugo is to use a clean, typography-first theme with minimal chrome, then tweak spacing, fonts, and colors.

Here are solid Hugo themes that already resemble Medium’s look & feel (reading-focused, wide text column, minimal UI):

1. PaperMod (Most popular starting point)
Best overall choice

Why it’s close to Medium

Clean, distraction-free layout

Excellent typography and spacing

Supports reading time, tags, author info

Light/dark mode like Medium

Very customizable via config (no heavy templating needed)

Good for

Blogs, essays, long-form writing

Repo

https://github.com/adityatelange/hugo-PaperMod
Why I recommend it
Many people start with PaperMod and tweak:

Font family → serif body font (to match Medium)

Increase max width of content

Reduce sidebar / navigation clutter

2. Hugo Bear Blog
Closest to “pure writing”

Why it’s close

Extremely minimal

Focus on text, almost no UI

Fast and simple

Tradeoff

Less “polished” out of the box

You’ll need to style it more to feel like Medium

Repo

https://github.com/janraasch/hugo-bearblog
Good if you want full control and don’t mind adding CSS yourself.

3. Typo
Typography-first, editorial vibe

Why it’s close

Emphasis on readable typography

Simple blog layout

Feels like an online magazine

Repo

https://github.com/tomowang/hugo-theme-typography
Recommended Starting Choice (Practical)
👉 Start with PaperMod, then adjust it toward Medium.

How to Make PaperMod Feel Even More Like Medium
Once installed:

1. Increase content width
params:
  contentWidth: "720px"
Medium articles are wider than most blog themes.

2. Use a serif body font
Add custom CSS:

body {
  font-family: ui-serif, Georgia, Cambria, "Times New Roman", Times, serif;
}
3. Reduce visual noise
Disable extras you don’t need:

params:
  showReadingTime: true
  showToc: false
  showBreadCrumbs: false
4. Medium-like spacing
.post-content p {
  line-height: 1.7;
  margin-bottom: 1.4em;
}
If You Want…
Closest out-of-the-box Medium clone → PaperMod

Ultra minimal writing platform → Bear Blog

Editorial / magazine feel → Typo

If you want, I can:

Pick one and generate a ready-to-use config.yaml

Help you match Medium typography exactly

Customize it for personal blog vs publication-style site

Just tell me which direction you want to go.

Du sagde:
lets create a new hugo site and apply the theme
ChatGPT sagde:
Great 👍 Let’s do this step by step, assuming you already have Hugo installed.

I’ll use PaperMod as the theme (best Medium-like starting point). You can swap themes later if you want.

1. Create a New Hugo Site
hugo new site my-medium-site
cd my-medium-site
You should now have:

my-medium-site/
├── archetypes/
├── content/
├── layouts/
├── static/
└── hugo.toml
2. Add PaperMod Theme
Option A: Using Git submodule (recommended)
git init
git submodule add https://github.com/adityatelange/hugo-PaperMod.git themes/PaperMod
Option B: Clone directly (simpler, less flexible)
git clone https://github.com/adityatelange/hugo-PaperMod.git themes/PaperMod
3. Configure Hugo to Use the Theme
Edit hugo.toml (or config.yaml if you prefer YAML).

Minimal Medium-like config
baseURL = "http://localhost:1313/"
languageCode = "en-us"
title = "My Writing"
theme = "PaperMod"

paginate = 10

[params]
  defaultTheme = "auto"
  ShowReadingTime = true
  ShowShareButtons = false
  ShowPostNavLinks = true
  ShowBreadCrumbs = false
  ShowCodeCopyButtons = true
  comments = false

  # Medium-ish layout
  contentWidth = "720px"

[menu]
  [[menu.main]]
    name = "Home"
    url = "/"
    weight = 1

  [[menu.main]]
    name = "About"
    url = "/about/"
    weight = 2
4. Create Your First Post
hugo new posts/hello-world.md
Edit the file:

---
title: "Hello World"
date: 2025-12-18
draft: false
---

This is my first post.

Medium-style writing focuses on **clarity**, *spacing*, and good typography.
5. Start the Development Server
hugo server -D
Open:

http://localhost:1313
You now have a clean, Medium-like Hugo blog running 🎉

6. (Optional) Make Typography More Medium-Like
Create a custom CSS file:

mkdir -p assets/css
touch assets/css/custom.css
Add this:

body {
  font-family: ui-serif, Georgia, Cambria, "Times New Roman", Times, serif;
}

.post-content p {
  line-height: 1.7;
  margin-bottom: 1.4em;
}
Then register it in hugo.toml:

[params]
  customCSS = ["css/custom.css"]
What We Can Do Next
I can help you:

Add author profile like Medium

Enable tags & publications

Adjust header, spacing, and fonts precisely

Prepare it for GitHub Pages / Netlify deployment

Just tell me the next step you want.



Vedhæft

Søg

Læs

Lav billede

Stemme
Der er ingen fil valgtDer er ingen fil valgt
ChatGPT kan tage fejl. Vi anbefaler at dobbelttjekke vigtig information. Se Cookiepræferencer.
