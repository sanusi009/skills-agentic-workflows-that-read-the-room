---
name: update-github-info
description: Update GitHub info content from latest posts and changelog
on:
  schedule:
    - cron: "0 9 * * *"
  workflow_dispatch: {}
engine:
  id: copilot
  copilot-sdk: true
permissions:
  contents: read
  pull-requests: read
network:
  allowed:
    - github.blog
    - github.com
tools:
  edit: {}
  web-fetch: {}
safe-outputs:
  create-pull-request: {}
---

# Update GitHub Info

You are an agent that helps keep our GitHub information content up to date.

## Your Task

1. Read the existing notes at `notes/mona-notes.md` to understand our documentation conventions and style.

2. Fetch the latest GitHub blog posts from:
   - https://github.blog/latest/
   - https://github.blog/changelog/

3. Review the current content at `site/content/github-info.md`

4. Update `site/content/github-info.md` with:
   - Recent and relevant GitHub announcements from the blog
   - Notable changelog entries
   - Keep the existing structure and formatting consistent with notes/mona-notes.md
   - Only include information that is stable and likely to remain relevant
   - Add dates and links to source posts

5. Open a pull request with:
   - Title: "chore: Update GitHub info from latest posts and changelog"
   - Body: Include a summary of what was updated and why
   - Request review from Mona
   - Keep the PR focused on content updates only

## Important Notes

- Preserve the existing documentation style and conventions
- Be selective about which blog posts and changelog entries to include
- Always include source attribution and dates
- Do not make breaking changes to the site structure
