[![Build Status](https://travis-ci.org/LibraryCarpentry/librarycarpentry.github.io.svg?branch=master)](https://travis-ci.org/LibraryCarpentry/librarycarpentry.github.io)

# The Library Carpentry Website

This is the repository for the new [Library Carpentry website](https://librarycarpentry.org).
Please submit additions and fixes as pull requests to [our GitHub repository](https://github.com/librarycarpentry/librarycarpentry.github.io).

*   [Setup](#setup)
*   [Previewing](#previewing)
*   [Development](#development)
    *   [Write a Blog Post](#blog)

Lessons are not stored in this repository:
please see the [Library Carpentry lessons page](https://librarycarpentry.org/lessons/)
for links to the individual lesson repositories.

> Library Carpentry is an open project,
> and we welcome contributions of all kinds.
> By contributing,
> you are agreeing that Library Carpentry may redistribute your work
> under [this license](/license.md),
> and to abide by The Carpentries' [code of conduct](http://docs.carpentries.org/topic_folders/policies/code-of-conduct.html).

## Setup <a name="setup"></a>

The website uses [Jekyll](http://jekyllrb.com/), a static website generator written in Ruby.
You need to have Version 2.0.0 or higher of Ruby and the package manager Bundler.
(The package manager is used to make sure you use exactly the same versions of software as GitHub Pages.)
After checking out the repository, please run:

```
$ bundle install
```

to install Jekyll and the software it depends on.
You may consult [Using Jekyll with Pages](https://help.github.com/articles/using-jekyll-with-pages/) for further instructions.

## Previewing <a name="previewing"></a>

Please do **not** use `jekyll build` or `jekyll serve` directly to build or view the website.
Instead, you should use the following commands:

*   `make` or `make commands`: list available commands.
*   `make serve`: build files locally and run a server at [http://0.0.0.0:4000/](http://0.0.0.0:4000/) for viewing.
    This is the best way to preview the site.
*   `make site`: build files locally, but do not serve them dynamically.
*   `make clean` removes the `_site` directory and any Emacs editor backup files littering the source directories.


## Development <a name="development"></a>

<a name="blog"></a>
To **write a blog post**,
create a file called  `_posts/YYYY/MM/YYYY-MM-DD-some-title.md`.
YYYY is the 4-digit year of the post, MM the 2-digit month, and DD the 2-digit day;
`some-title` can be any hyphenated string of words that do not include special characters such as quotes.
Please do *not* use underscores or periods in the names.
When published,
your blog post will appear as `http://librarycarpentry.org/blog/YYYY/MM/DD/some-title`.

The YAML header of a blog post must look like this:

~~~
---
layout: blog-post
authors: ["Your Name"]
title: "A Title-Cased Title for the Post"
category: blog
---
~~~

Note also that `authors` is a list---if the post has more than one author,
please format the list like this:

~~~
...
authors: ["First Author", "Second Author", "Third Author"]
...
~~~

rather than running all the authors' names together in one long string.



## Deployment with GitHub Actions

The default branch for this repository is `main`. All pull requests should be made from there.
Pushing to the `main` branch triggers GitHub Actions. The script:
- checks that the YAML headers in pages and blog posts are valid;
- gets the latest version of the data feeds for the list of past and upcoming workshops;
- builds the website;
- pushes to the `master` branch.

GitHub pages takes care of generating the website from the content of the `master` branch. Note that because of current limitations with GitHub, we need to use the `master` branch and keep the name of the repository `librarycarpentry.github.io` to ensure that all our lessons are available from `https://librarycarpentry.org/<name-of-lesson-repository>`.
