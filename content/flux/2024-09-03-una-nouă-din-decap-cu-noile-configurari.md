---
title: Una nouă din Decap cu noile configurari
draft: false
date: 2024-09-03 09:21
---
## Înainte de code block acum e un headline frumușel

```
collections: # A list of collections the CMS should be able to edit
  - name: 'posts' # Used in routes, ie.: /admin/collections/:slug/edit
    label: 'Posts' # Used in the UI
    label_singular: 'Post' # Used in the UI, ie: "New Post"
    description: >
      The description is a great place for tone setting, high level information, and editing
      guidelines that are specific to a collection.
    folder: 'content/posts'
    slug: '{{year}}-{{month}}-{{day}}-{{slug}}'
    summary: '{{title}} -- {{year}}/{{month}}/{{day}}'
    create: true # Allow users to create new documents in this collection
    view_filters:
      - label: Posts With Index
        field: title
        pattern: 'This is post #'
      - label: Posts Without Index
        field: title
        pattern: front matter post
      - label: Drafts
        field: draft
        pattern: true
    view_groups:
      - label: Year
        field: date
        pattern: \d{4}
      - label: Drafts
        field: draft
    fields: # The fields each document in this collection have
      - { label: 'Title', name: 'title', widget: 'string', tagname: 'h1' }
      - { label: 'Draft', name: 'draft', widget: 'boolean', default: false }
      - {
          label: 'Publish Date',
          name: 'date',
          widget: 'datetime',
          format: 'YYYY-MM-DD HH:mm',
          default: '{{now}}',
        }
      - label: 'Cover Image'
        name: 'image'
        widget: 'image'
        required: false
        tagname: ''

      - { label: 'Body', name: 'body', widget: 'markdown', hint: 'Main content goes here.' }
```
