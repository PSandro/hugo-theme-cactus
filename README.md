## Cactus

This is a stripped down version of cactus. Trying to avoid JavaScript and keep things simple and clean.

A hugo theme for personal blog. Fork from hexo theme [cactus](https://github.com/probberechts/hexo-theme-cactus) created by @probberechts.

## Config

### Color themes

```toml
[params]

  colortheme = "white" # dark, light, white, or classic
```

### Navigation

```toml
# Main menu which appears below site header.
[[menu.main]]
name = "Home"
url = "/"
weight = 1

[[menu.main]]
name = "All posts"
url = "/posts"
weight = 2

[[menu.main]]
name = "Tags"
url = "/tags"
weight = 3

[[menu.main]]
name = "About"
url = "/about"
weight = 4
```

### Homepage settings

* description: description will be displayed in the homepage. Markdown syntax is supported in the description string.
```toml
[params]

  description = "Hugo is a general-purpose website framework. Technically speaking, Hugo is a static site generator. Unlike systems that dynamically build a page with each visitor request, Hugo builds pages when you create or update your content. Since websites are viewed far more often than they are edited, Hugo is designed to provide an optimal viewing experience for your website’s end users and an ideal writing experience for website authors."
```

* set your main section (used as the link for the "writings" title on the homepage)

```toml
[params]
  mainSection = "posts"
```

* change the default main section title from Writings, to something else:

```toml
[params]
  mainSectionTitle = "Blog"
```

* Show only the 5 most recent posts (default)

```toml
[params]
  showAllPostsOnHomePage = false
  postsOnHomePage = 5
```
* show all posts

```toml
[params]
  showAllPostsOnHomePage = true
  postsOnHomePage = 5 # this option will be ignored
```

* show tagsoverview (default) or not
* 
```toml
[params]
  tagsOverview = true
```

* display the table of contents inline on blog posts, rather than as part of the navigation menu:

```toml
[params]
  tocInline = true
```

* show projects list (default) or not.

```toml
[params]
  showProjectsList = true
  projectsUrl = "https://github.com/monkeyWzr"
```

Projects section will not be shown if no data file is detected. See [Projects list](#projects-list) below.

### Projects list

Create your projects data file `data/projects.yaml|toml|json`. Hugo support yaml, toml and json formats.
for former hexo cactus users: please assign your json array to a `list` key.

for example, `data/projects.json`:
```json
{
   "list": [
      {
         "name":"Hexo",
         "url":"https://hexo.io/",
         "desc":"A fast, simple & powerful blog framework"
      },
      {
         "name":"Font Awesome",
         "url":"http://fontawesome.io/",
         "desc":"The iconic font and CSS toolkit"
      }
   ]
}
```

### Social media links

```toml
[[params.social]]
  name = "github"
  link = "https://github.com/monkeyWzr"

[[params.social]]
  name = "email"
  link = "monkeywzr@gmail.com" # no need for "mailto:" at the start

[[params.social]]
  name = "linkedin"
  link = "https://www.linkedin.com/in/monkeywzr/"
```

The `name` key expects the name of a [Font Awesome icon](https://fontawesome.com/icons?d=gallery&s=brands).

### Copyright

Assign your copy right to `.Site.Copyright`. Cactus will append current year to the head.

TODO: Customizable copyright year

```toml
copyright = "Zeran Wu" # cactus theme will use site title if copyright is not set
```

### highlight

Use hugo's built-in [syntax highlighting](https://gohugo.io/getting-started/configuration-markup#highlight).

default config:

```toml
[markup]
  [markup.highlight]
    codeFences = true
    guessSyntax = false
    hl_Lines = ""
    lineNoStart = 1
    lineNos = false
    lineNumbersInTable = true
    noClasses = true
    style = "monokai"
    tabWidth = 4
```

### RSS

The rss feed is not generated by default. you can enable it in your site config:

```toml
[params]
  rss = true
```

The rss link will be `https://example.com/index.xml` assuming your `baseURL` is set to `https://example.com/`

Please also check [Configure RSS](https://gohugo.io/templates/rss/#configure-rss)

### Mathjax

Cactus supports mathjax. Just add `mathjax` option in your site config:
```toml
[params]
  mathjax = true  # not required
```

You can also enable/disable mathjax per post. In your posts' front matter, add:
```yaml
mathjax: true # or false
```

The site config will be ignored when `mathjax` option exists in front matter.

### Archive 
Pagination on posts archive can be disabled to show all posts in chronological order

```toml
[params]
  showAllPostsArchive = true # or false (default)
```

## TODOS

- [ ] More comments engines
- [x] RSS
- [ ] I18n
- [x] Analytics
- [ ] Local Search
- [ ] toc template
- [ ] Customizable copyright year
- [ ] gallery
- [ ] expose [mathjax configuration](https://docs.mathjax.org/en/latest/web/configuration.html#web-configuration) 

## License

MIT
