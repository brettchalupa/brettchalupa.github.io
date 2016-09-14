---
title: My Shopify Theme Development Workflow
date: 2016-09-14 12:04:00 -07:00
categories:
- shopify
tags:
- note
- shopify
- workflow
description: A simple and effective workflow for building and maintaining Shopify
  themes.
---

I have been doing development work on quite a eandful Shopify sites recently, and I have come up with a workflow that has been working well. Here is how I arrived at the workflow and what it looks like.

## Requirements

I wanted Shopify development to be as close to my normal workflow as possible.

### Use Editor of Choice

The easiest way to make changes to a Shopify theme is to make changes directly in the Shopify admin.

![shopify-theme-editor.png](/uploads/shopify-theme-editor.png)

The theme editor is competent, but I strongly prefer working in my editor of choice (vim). The theme editor has no split views or theme customization.

### Track Theme Changes with Git

I strongly value being able to track the changes to a codebase over time, so it is important to be able to manage the theme's history with Git. It is nice to be able to work with branches for experiments, use `git bisect` to identify when bugs were introduced, and revert changes as needed.

### Make Use of a Staging (a.k.a. Test) Environment

For non-trivial theme changes, it is not a great idea to make the changes on the live site. I wanted the workflow to be able to easily support pushing the theme changes up to a Staging environment for review before making them live. This also allows more traditional releases to the live site to be created.

## Things To Watch Out For

1. Making direct changes to the theme in the Shopify admin
2. Making changes before the CLI is watching for those changes

## Additional Reading

-----

Looking for Shopify theme development help? [Reach out and let me know how I can help.](/hire/)
