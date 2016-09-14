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

### Multiple Store Support

For non-trivial theme changes, it is not a great idea to make the changes on the live site. I wanted the workflow to be able to easily support pushing the theme changes up to a Staging environment for review before making them live. This also allows more traditional releases to the live site to be created.

## The Workflow

The workflow, simplified, is: manage the theme source locally by making changes and committing those changes with Git while running a command line tool to watch for changes and update the theme on the Shopify store.

It is worth noting that this workflow makes use of the command line. It is not anything too intensive -- just a few simple commands.

1. Install [Theme Kit](http://themekit.cat/install/) - Theme Kit is a cross-platform command line tool for Shopify theme development. It is written in Go, which means it has no external dependencies like Ruby and is fast. Once it is all setup, the `theme` command should be available. This workflow is for Theme Kit version `v0.4.2`.
2. Create a directory to work with the theme - `mkdir site-name`
3. Create a file called `config-example.yml` in the theme directory and add the following to it:
  ```
  development:
    store: STORE_NAME_HERE.myshopify.com
    password: ADD_PASSWORD_HERE
    bucket_size: 40
    refill_rate: 2
    ignore_files:
      - "*.swp"
      - "*~"
      - "config/settings_data.json"
  ```
  The `config-example.yml` is used by Theme Kit to manage the different store environment settings. An example file is used since it does not contain secrets and can be checked into Git.
4. Initialize a Git repository for the theme - `git init`
5. Create a `.gitignore` file with the following lines:
  ```
  config.yml
  config/settings_data.json
  ```
  This will prevent secrets from the soon-to-be-created `config.yml` from being checked in, as well as ignore `config/settings_data.json` which is store-specific and does not need to be in Git.
6. Copy the config example to the file Theme Kit will use - `cp config-example.yml config.yml`
7. Create a private app in your Shopify store, which will give you a password.
8. Set the store URL and password in the `config.yml`.
9. Start Theme Kit to watch for changes - `theme watch`
10. Make changes and checkout those changes on your store
11. Make Git commits and develop away!

## Things To Watch Out For

1. Making direct changes to the theme in the Shopify admin
2. Making changes before the CLI is watching for those changes

## Additional Reading

-----

Looking for Shopify theme development help? [Reach out and let me know how I can help.](/hire/)
