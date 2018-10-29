Flatdoc
=======

Flatdoc is a small JavaScript file that fetches Markdown files and renders them
as full pages. Essentially, it's the easiest
way to make open source documentation from *Readme* files.

 * No server-side components
 * No build process needed
 * Deployable via GitHub Pages
 * Can fetch GitHub Readme files
 * Gorgeous default theme (and it's responsive)
 * Just create an HTML file and deploy!

*Current version: [v0.9.0][dist]*

[![Build Status](https://travis-ci.org/rstacruz/flatdoc.svg?branch=gh-pages)](https://travis-ci.org/rstacruz/flatdoc)

Getting started
---------------

Create a file based on the template, which has a bare DOM, link to the
scripts, and a link to a theme. It will look something like this (not exact).
For GitHub projects, simply place this file in your [GitHub pages] branch and
you're all good to go.

*In short: just download this file and upload it somewhere.*

The main JS and CSS files are also available in [npm] and [bower].

[Default theme template >][template]

[Blank template >][blank]

[bower]: http://bower.io/search/?q=flatdoc
[npm]: https://www.npmjs.org/package/flatdoc

### Via GitHub

To fetch a Github Repository's readme file, use the `Flatdoc.github` fetcher.
This will fetch the Readme file of the repository's default branch.

``` javascript
Flatdoc.run({
  fetcher: Flatdoc.github('USER/REPO')
});
```

You may also fetch another file other than the Readme file, just specify it as
the 2nd parameter.

``` javascript
Flatdoc.run({
  fetcher: Flatdoc.github('USER/REPO', 'Changelog.md')
});
```

After you've done this, you probably want to deploy it via [GitHub Pages].

[GitHub Pages guide >][GitHub Pages]

### Via a file

You may also fetch a file. In this example, this fetches the file `Readme.md` in
the same folder as the HTML file.

``` javascript
Flatdoc.run({
  fetcher: Flatdoc.file('Readme.md')
});
```

You may actually supply any URL here. It will be fetched via AJAX. This is
useful for local testing.

``` javascript
Flatdoc.run({
  fetcher: Flatdoc.file('http://yoursite.com/Readme.md')
});
```
