[![License: GPL v3](https://img.shields.io/badge/License-GPLv3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)

# 🔗 GitHub Pages URL Shortener

This is a minimal URL shortener that can be entirely hosted on GitHub pages. It
does not need the maintenance of any servers or databases and can be hosted
entirely on GitHub for free!

## 👨‍🏫 Demo

1. [your-github-url/1](https://erdincozsertel.github.io/gh-pages-url-shortener/1) should link to this repo.

1. To add a new short link, add an issue with the title being the link you want
   to shorten (including the `http(s)://`) to
   [https://github.com/erdincozsertel/gh-pages-url-shortener-db/issues](https://github.com/erdincozsertel/gh-pages-url-shortener-db/issues).

1. The newly created short url can be accessed via `your-github-url/{issue_number}`

## ☕️ Features

1. Unlike many URL shorteners, this one ~~does not need a database~~ uses a
   "database" in the form of GitHub issues and can be entirely hosted on GitHub
   pages.

1. There is no need for the pound symbol - short URLs look clean like this:
   `your-github-url/1` instead of looking like this: `your-github-url/#1`.

## 💡 How does this work?

_Thanks to @kidGodzilla for the pretty neat explanation
[here](https://github.com/nelsontky/gh-pages-url-shortener/issues/5#issuecomment-728040879)._

> 1. 404.html handles all requests
> 1. Small javascript snippet fetches a JSON representation of the GitHub issue
>    via the JSON API, and redirects to the issue title, as a URL.
> 1. Profit?


1. Fork the repo before cloning your fork.
1. Set up GitHub pages for your forked repo.
   1. In your forked repo, **click the Settings tab** and scroll down to the
      GitHub Pages section.
   1. Then select the **main branch** source and click on the **Save** button.
   1. <img src="https://i.imgur.com/kjinFX9.png" alt="How to create GitHub page" height="176px">
1. If you are using GitHub page's default domain i.e. Something like
   `https://<username>.github.io/<repo-name>/`
   1. Change `var PATH_SEGMENTS_TO_SKIP = 0;` at the top of `404.html` to
      `var PATH_SEGMENTS_TO_SKIP = 1;`.
      1. This is as GitHub domains have an additional path segment (the repo
         name) after the host name.
1. Create a new repo as a database. (Or you could use your forked repo)
   1. Update `var GITHUB_ISSUES_LINK = "<your-github-issues-link>";` at the top
      of `404.html` accordingly afterwards.
      1. Format for `GITHUB_ISSUES_LINK`:
         `https://api.github.com/repos/{owner}/{repo}/issues/`
      1. Remember the trailing `/`!
1. Push your changes to your forked repo, and your low cost and cool as heck URL
   shortener will be ready for use!

## 🍴 Featured forks

To feature your fork here, edit this section and open a PR!

- [eexit.github.io/s](https://github.com/eexit/s) - Created a bash script that
  allows for shortening of URLs straight on the command line! Check out his
  script
  [here](https://github.com/nelsontky/gh-pages-url-shortener/issues/49#issue-745134937).
- [gh-short-url](https://github.com/mayandev/gh-short-url) - A npm command line
  tool that uses GitHub pages to convert short URLs.
