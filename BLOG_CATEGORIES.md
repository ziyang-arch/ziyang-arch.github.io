# Blog Categories Guide

Your blog supports **categories** (sections/channels) that act as labels for organizing your posts.

## Available Categories

- **Technology and Moral** - Posts about ethics, philosophy, and technology
- **Miscellany** - General posts, various topics
- **Musing** - Reflective thoughts, personal reflections, contemplative writing

## How to Add Categories to a New Post

### Method 1: Using Hugo Command

```bash
hugo new posts/my-new-post.md
```

Then edit the file and add your category:

```yaml
---
title: "My New Post"
date: 2026-02-13
draft: false
categories: ["Technology and Moral"]  # Add your category here
tags: []
---
```

### Method 2: Create File Manually

Create a new `.md` file in `content/posts/` with front matter:

```yaml
---
title: "Your Post Title"
date: 2026-02-13
draft: false
categories: ["Musing"]  # Choose one or more categories
tags: []
---

Your post content here...
```

## Category Format

- **Single category**: `categories: ["Technology and Moral"]`
- **Multiple categories**: `categories: ["Technology and Moral", "Miscellany"]`
- Categories are case-sensitive, so use exact spelling: "Technology and Moral" (capital T, capital M)

## Adding New Categories

Simply use a new category name in your post's front matter. Hugo will automatically:
- Create a category page at `/categories/your-category-name/`
- Show the category as a label on your post
- Group posts by category

## Examples

- Technology and Moral post: `categories: ["Technology and Moral"]`
- Miscellany post: `categories: ["Miscellany"]`
- Musing post: `categories: ["Musing"]`
- Post in multiple categories: `categories: ["Technology and Moral", "Miscellany"]`

## Where Categories Appear

- On each blog post page (as labels/links)
- On the blog listing page
- On category archive pages (e.g., `/categories/technology-and-moral/`)
- In the site navigation (if configured)
