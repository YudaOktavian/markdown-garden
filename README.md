## Markdown Garden

A little corner of the Internet that's all about Markdown.

### Installing Locally

This guide assumes that you already have Git, Ruby, RubyGems, and Bundler
installed on your development machine.

```
git clone git://github.com/chrisalley/markdown-garden.git
cd markdown-garden
bundle
bundle exec middleman
```

Then visit <http://localhost:4567> to view the website.

### Making Changes Locally

You can edit the guides in `/source/guides`. These guides should all
be valid [CommonMark][commonmark].

Guide file and directory names should be a lowercase, parameterised, version of
the guide's title, using [stringex][stringex]-style parameterisation. Guides
that have subguides should be placed in a subdirectory using the same naming
convention; the guide itself should have the filename `index.md`.

To add new guides or reorder existing guides, edit `/data/guides.yml`. The
table of contents (including links) will be automatically generated based on the
convention used in the YAML file and directory/file names of the guides.

Once changes have been made, run the following command to generate a new static
version of the site:

```
bundle exec middleman build
```

Then visit <http://localhost:4567> to view the changes.

### Publishing Changes

Once changes are ready to be pushed, commit and push to the master branch (or
[create a pull request][new-pull-request]
if you don't have permission).

```
git add -A
git commit -m "Update the website with new awesome changes"
git push origin master
```

Now publish the website:

```
bundle exec rake publish
```

This will build a static version of the website and replace the contents of the
`gh-pages` branch with this new version. The changes will now be live on
[the GitHub Pages site][github-pages].

[commonmark]: http://www.commonmark.org
[stringex]: https://github.com/rsl/stringex
[new-pull-request]: https://github.com/chrisalley/markdown-garden/compare
[github-pages]: https://chrisalley.github.io/markdown-garden
