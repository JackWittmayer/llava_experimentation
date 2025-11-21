# Jack Wittmayer's Personal Website

A minimal blog-style website built with HTML, CSS, and Python. Write your posts in Markdown and they'll be automatically converted to HTML.

## Getting Started

### Setup (First Time)

The repository includes a virtual environment setup. To initialize it:

```bash
# Run the setup script (one-time only)
./setup.sh

# Or manually:
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

### Local Development

To run this site locally:

```bash
# Start a local web server
python3 -m http.server 8000
```

The site will be available at `http://localhost:8000`

## Structure

```
.
├── index.html           # Main landing page
├── about.html           # About page
├── styles.css           # Stylesheet for the website
├── build_posts.py       # Python script to convert Markdown to HTML
├── _posts/              # Directory containing Markdown blog posts
│   ├── 2025-11-05-first-post.md
│   ├── 2025-11-10-learning-rust.md
│   ├── 2025-11-15-building-tools.md
│   └── 2025-11-18-thoughts-on-ai.md
├── posts/               # Output directory with generated HTML files
│   ├── first-post.html
│   ├── learning-rust.html
│   ├── building-tools.html
│   └── thoughts-on-ai.html
└── README.md            # This file
```

## Writing Blog Posts

Blog posts are written in Markdown format and stored in the `_posts/` directory.

### Post File Format

Name your files with the date prefix: `YYYY-MM-DD-post-title.md`

Example: `2025-11-20-my-new-post.md`

### Post Structure

Each post should start with YAML frontmatter:

```markdown
---
title: My Blog Post Title
date: 2025-11-20
description: A short description of your post for the index page.
---

Your markdown content goes here. You can use:
- Lists
- **Bold** and *italic*
- Links [like this](https://example.com)
- And more standard Markdown features
```

### Building Posts

After writing or editing posts in `_posts/`, activate the virtual environment and run the build script:

```bash
# Option 1: Use the build script (recommended)
./build.sh

# Option 2: Manually activate and run
source .venv/bin/activate
python3 build_posts.py
deactivate
```

This will:
1. Read all `.md` files from `_posts/`
2. Parse the YAML frontmatter (title, date, description)
3. Convert Markdown to HTML
4. Generate full HTML pages in `posts/`

The generated HTML files automatically include the navigation header and footer.

## Customization

Edit the following files to personalize your site:

1. **index.html** - Update the bio section and customize the latest post section
2. **about.html** - Update your about page content
3. **styles.css** - Customize colors, fonts, and layout
4. **_posts/*.md** - Write your blog posts in Markdown

## Deployment

This site is set up for GitHub Pages:

1. Build any new posts: `./build.sh`
2. Commit your changes: `git add . && git commit -m "Your message"`
3. Push to the `main` branch: `git push`
4. GitHub will automatically serve your site at `https://JackWittmayer.github.io`

Note: Always run `./build.sh` after creating or editing posts to generate the HTML files in the `posts/` directory before pushing.

## License

All rights reserved.
