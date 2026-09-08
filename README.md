# Parker's Place

A deliberately small personal website built with Markdown, Jekyll, CSS, and GitHub Pages.

## Local development

Install Ruby and Bundler, then:

```bash
bundle install
bundle exec jekyll serve --livereload
```

Open <http://127.0.0.1:4000>.

## Deploy

Push the repository to GitHub on the `main` branch. GitHub Actions builds and deploys the site to GitHub Pages.

GitHub Pages must be enabled in the repository settings with **GitHub Actions** as the source.

## Add a post

Create a Markdown file under `_posts/` using:

```text
YYYY-MM-DD-title.md
```

Then add YAML front matter, for example:

```yaml
---
title: "My post"
date: 2026-09-08
---
```

For an OpenSilicon post, add:

```yaml
project: opensilicon
```
