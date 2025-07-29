# Adam Lewis Portfolio Website

A Jekyll-based portfolio website showcasing recent projects and posts.

**Live Site**: [https://adam-d-lewis.github.io/](https://adam-d-lewis.github.io/)

## Overview

This is a **private development repository** that automatically publishes to a public GitHub Pages site. The workflow allows for private development while maintaining a clean, public presence.

## Quick Start

### Local Development

1. **Install dependencies**:
   ```bash
   bundle install
   ```

2. **Start local server**:
   ```bash
   bundle exec jekyll serve
   ```
   
3. **View your site**: Open [http://localhost:4000](http://localhost:4000)

The site will automatically regenerate when you make changes to files.

## Adding New Posts

### Step 1: Create the Post File

Create a new file in the `_posts/` directory with the naming convention:
```
YYYY-MM-DD-title-with-dashes.md
```

**Example**: `2024-03-15-my-new-project.md`

### Step 2: Add Front Matter

Each post must start with YAML front matter:

```yaml
---
title: Your Post Title Here
image: /assets/images/your-image.png
description: Brief description of your post
company: Your Company Name (or "Personal Project")
date: 2024-03-15
layout: post
---
```

**Required fields**:
- `title`: The post title
- `date`: Format as `YYYY-MM-DD`
- `layout: post`

**Optional fields**:
- `image`: Featured image path
- `description`: Meta description for SEO
- `company`: Organization or "Personal Project"

### Step 3: Write Your Content

Add your content below the front matter using Markdown:

```markdown
---
title: My Amazing Project
date: 2024-03-15
layout: post
---

## Introduction

This is my new project about...

### Key Features

- Feature 1
- Feature 2
- Feature 3

Check out the [live demo](https://example.com) or view the [source code](https://github.com/username/repo).
```

## Publishing Workflow

### Automatic Publishing

The site uses **GitHub Actions** for automatic deployment:

1. **Push to master**: Any push to the `master` branch triggers deployment
2. **Build process**: Jekyll builds the site automatically
3. **Public deployment**: Built site is pushed to the public repository
4. **Live in minutes**: Changes appear at [https://adam-d-lewis.github.io/](https://adam-d-lewis.github.io/) within 2-3 minutes

### Manual Deployment

You can also trigger deployment manually:
1. Go to the "Actions" tab in GitHub
2. Select "Build Jekyll"
3. Click "Run workflow"

## Development Commands

### Basic Commands
```bash
# Install dependencies
bundle install

# Serve locally with live reload
bundle exec jekyll serve

# Build the site
bundle exec jekyll build

# Serve with draft posts visible
bundle exec jekyll serve --drafts

# Serve on different port
bundle exec jekyll serve --port 4001

# Production build
JEKYLL_ENV=production bundle exec jekyll build
```

### Troubleshooting Local Development
- If gems are missing: `bundle install`
- If server won't start: Check Ruby version compatibility
- For port conflicts: Use `--port 4001` or another port

## Site Features

- **Responsive Design**: Works on desktop, tablet, and mobile
- **Blog Pagination**: 4 posts per page
- **SEO Optimized**: Meta tags, sitemap, RSS feed
- **Math Support**: MathJax for mathematical expressions
- **Charts**: Chart.js integration for data visualization
- **Comments**: Disqus integration (configured)
- **Analytics**: Google Analytics tracking

## File Structure

```
├── _posts/           # Blog posts (YYYY-MM-DD-title.md)
├── _projects/        # Project collection
├── _pages/           # Static pages
├── assets/
│   ├── css/         # Stylesheets and Sass files
│   ├── images/      # Images and media
│   └── js/          # JavaScript files
├── _config.yml      # Jekyll configuration
├── Gemfile          # Ruby dependencies
└── README.md        # This file
```

## Content Guidelines

### Images
- Store images in `/assets/images/`
- Use descriptive filenames
- Optimize for web (< 500KB recommended)
- Reference in posts: `/assets/images/filename.png`

### Post Categories
Posts automatically appear in:
- **Recent Posts**: Latest 3 posts on homepage
- **All Posts**: Complete list in sidebar
- **Blog Page**: Paginated list at `/blog/`

## Deployment Architecture

```
┌─────────────────────────────────────┐
│ Private Repo                        │
│ (private.adam-d-lewis.github.io)    │
│                                     │
│ • Development                       │
│ • Source code                       │
│ • Configuration                     │
└──────────────┬──────────────────────┘
               │ Push to master
               ▼
┌─────────────────────────────────────┐
│ GitHub Actions                      │
│                                     │
│ • Jekyll build                      │
│ • Asset compilation                 │
│ • Site generation                   │
└──────────────┬──────────────────────┘
               │ Deploy
               ▼
┌─────────────────────────────────────┐
│ Public Repo                         │
│ (adam-d-lewis.github.io)           │
│                                     │
│ • Built site files                  │
│ • GitHub Pages hosting              │
│ • Public access                     │
└─────────────────────────────────────┘
```

## Security Notes

- **Private Development**: Source code remains private
- **Public Output**: Only built site files are public
- **Token Access**: GitHub Actions uses `GH_TOKEN` for deployment
- **No Secrets**: No sensitive data is exposed in the public repository

## Getting Help

### Common Issues

1. **Posts not appearing**: Check filename format (`YYYY-MM-DD-title.md`) and date format in front matter
2. **Build failures**: Check YAML syntax in front matter
3. **Images not loading**: Verify image paths start with `/assets/images/`
4. **Local server issues**: Try `bundle exec jekyll clean` then `bundle exec jekyll serve`

### Resources

- [Jekyll Documentation](https://jekyllrb.com/docs/)
- [Markdown Guide](https://www.markdownguide.org/)
- [GitHub Pages Documentation](https://docs.github.com/en/pages)

---

**Live Site**: [https://adam-d-lewis.github.io/](https://adam-d-lewis.github.io/)