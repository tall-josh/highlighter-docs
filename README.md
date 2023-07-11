# Highlighter Public Documentation

This repo contains public documentation for Silverpond's Highlighter product.

See /content folder for details.

This documentation site uses Zola to generate a static website. Follow their [installation page](https://www.getzola.org/documentation/getting-started/installation/) to install Zola and get started. For ease of use, there's a [justfile](https://github.com/casey/just) for common Zola actions.

Or you can use flakes (eg., `nix develop` or direnv (.envrc) to install Zola and setup the environment.


### Deployment
[![Netlify Status](https://api.netlify.com/api/v1/badges/9b184225-5c69-4c91-8c19-5c6104c96108/deploy-status)](https://app.netlify.com/sites/highlighter-docs/deploys)

The static website is deployed via [Netlify](https://netlify.app/), follwing Zola's [instructions](https://www.getzola.org/documentation/deployment/netlify/):
* The site is deployed to [https://highlighter-docs.netlify.app/](https://highlighter-docs.netlify.app/) when MRs are merged to `main` in [Github](https://github.com/silverpond/highlighter-docs).
* Deploys are password protected using [Basic Password Protection](https://docs.netlify.com/visitor-access/site-protection/#basic-password-protection-versus-team-login-protection) by Netlify. Password is in 1Password "Silverpond Shared" vault.
* There is separate prod site, we will remove the password when it is ready for public view
* Each MR will will create a [Deploy Preview URL for review](https://docs.netlify.com/site-deploys/deploy-previews/)
* Deploys are added as comments to a Github MR
* Deploy notifications are sent via slack to #highlighter-docs

### Working with the Repo

Clone the repo including submodules.

The repo also includes a `justfile` for common interactions with the repo.

Update content in /content and create an MR.
