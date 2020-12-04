---
title: "Initialize Hugo"
weight: 1
draft: false
lastmod: 2020-11-5
type: docs
layout: two-col
---
{row-divider}
Before we begin, install Hugo on your system. => [Hugo Documentation](https://gohugo.io/getting-started/installing/)
{divider}
{row-divider}
#### Initialize your repo
Create a new Hugo site and initialize it as a git repo.

Then, we can add the Clyde theme.
{divider}
``` bash
hugo new site example-site
cd example-site
git init
git submodule add https://github.com/gewenyu99/clyde.git themes/clyde
```
{row-divider}
#### Configure your Hugo site to use Clyde
Copy the toml config on the right into your `config.toml` file.

We'll cover the details of configuring your site in another section.
{divider}
{{<code/float-window>}}
{{< tabs tabTotal="1" tabID="1" tabName1="config.toml">}}
{{% tab tabNum="1" %}}
``` toml
baseURL = "http://example.org/"
languageCode = "en-us"
title = "Example Application"
theme = "clyde"
pygmentsUseClasses=true
publishDir = "docs"
relativeURLs = true
canonifyURLs = true


[markup]
  [markup.goldmark]
    [markup.goldmark.extensions]
      definitionList = true
      footnote = true
      linkify = true
      strikethrough = true
      table = true
      taskList = true
      typographer = true
    [markup.goldmark.parser]
      attribute = true
      autoHeadingID = true
      autoHeadingIDType = "github"
    [markup.goldmark.renderer]
      hardWraps = false
      unsafe = false
      xhtml = false
      
[params]
    #colors
    secondary = "#1E1F21"
    sidebar_bg = "#f6f6f8"
    sidebar_primary = "#1E1F21"
    primary = "#fff"
    accent = "#e3413a"
    grey200 = "#F9F9FA"
    grey600 = "#969DAC"
    grey_head= "#EFEFF3"

[outputs]
    section = ["JSON", "HTML"]
```
{{% /tab %}}
{{< /tabs >}}
{{</code/float-window>}}
{row-divider}
#### Add your first document
Hugo renders Markdown content from the `content` folder.

Clyde renders its primary documentation style content from the `content/docs` folder. You can still use other folders to render custom static html content.

`content/docs/first-category/_index.md` specifies the way the category menu will be rendered, it's an empty markdown file with frontmatter to configure the application. In fact, Clyde will render a menu for any markdown file with a `type : "category"` in the frontmatter.

`content/docs/first-category/content.md` is a document under the _index.md first category file. It uses a single column layouts, more on layouts later.
{divider}
{{<code/float-window>}}
{{< tabs tabTotal="2" tabID="2" tabName1="content/docs/first-category/_index.md" tabName2="content/docs/first-category/content.md">}}
{{% tab tabNum="1" %}}
``` md
---
title: "First Category"
icon: "icon-layers"
type : "category"
weight: 1
---
```
{{% /tab %}}

{{% tab tabNum="2" %}}
``` md
---
title: "Doc"
weight: 2
draft: false
lastmod: 2020-11-5
type: docs
layout: single-col
---

#### Hi!
```
{{% /tab %}}
{{< /tabs >}}
{{</code/float-window>}}

{row-divider}
#### Testing it out
That's it, you can start writing pages in markdown and see them updated in real time!
{divider}
```bash 
hugo serve

# if you want to include drafts

hugo serve -D
```
{row-divider}
#### Build it
That's it, you can start writing pages in markdown and see them updated in real time!
{divider}
```bash 
hugo

# if you want to include drafts

hugo -D
```
