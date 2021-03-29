---
title: "Initialize Hugo"
weight: 1
draft: false
lastmod: 2020-11-5
type: docs
layout: two-col
---
{row-divider}

{{< load-photoswipe >}} 

Before we begin, install `Hugo` on your system.

[Hugo Documentation](https://gohugo.io/getting-started/installing/)

You'll also need `git` for source control and an IDE you're comfortable with. Clyde was written with `Visual Studio Code`.
{divider}
{row-divider}
#### Initialize your repo
Create a new Hugo site and initialize it as a git repo.

Then, we can add the Clyde theme.
{divider}
{{%code/code-block%}}
``` bash {linenos=table}
hugo new site example-site
cd example-site
git init
git submodule add https://github.com/DNAstack/clyde.git themes/clyde
```
{{%/code/code-block%}}

{row-divider}
#### Configure your Hugo site to use Clyde
Copy the toml config on the right into your `config.toml` file.

We'll cover the details of configuring your site in another section.
{divider}
{{<code/float-window>}}
{{< tabs tabTotal="1" tabID="1" tabName1="config.toml">}}
{{% tab tabNum="1" %}}
``` toml
baseURL = "http://example.org/clyde-example-app/"
languageCode = "en-us"
title = "Clyde Sample App"
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
      unsafe = true
      xhtml = false
      
[params]
    #colors
    secondary = "#1E1F21"
    sidebar_bg = "#f6f6f8"
    sidebar_primary = "#1E1F21"
    primary = "#fff"
    accent = "#e3413a"
    grey200 = "#F9F9FA"
    grey600 = "#1E1F21"
    grey_head= "#EFEFF3"

    logo = "/default_button.png"

    home = "/docs/"

    heading_font = "Poppins"
    body_font = "Roboto"
    code_font = "Source Code Pro"
[outputs]
    section = ["HTML"]
    home = ["JSON", "HTML"]

[menu]
    [[menu.main]]
        identifier = "home"
        pre = "<i class='icon-home'></i>"
        name = "Home"
        url = "/"
        weight = -999
    [[menu.main]]
        identifier = "git"
        pre = "<i class='icon-github'></i>"
        name = "Github"
        url = "https://github.com/gewenyu99/clyde-example-app"
        weight = 1
```
{{% /tab %}}
{{< /tabs >}}
{{</code/float-window>}}
{row-divider}
#### Add your first document
Hugo renders Markdown content from the `content` folder.

Clyde renders its primary documentation style content from the `content/docs` folder. You can still use other folders to render custom static html content.

Take the example: `content/docs/quick-start/_index.md`. The file `_index.md` specifies the way the category menu will be rendered, it's an empty markdown file with frontmatter to configure the application. In fact, Clyde will render a menu for any markdown file with a `type : "category"` in the frontmatter.

`content/docs/quick-start/init.md` (this page) is a document under the _index.md quick-start category file. It uses a two column layouts, more on layouts [here](/docs/layout/).
{divider}
{{<code/float-window>}}
{{< tabs tabTotal="2" tabID="2" tabName1="_index.md" tabName2="quickstart.md">}}
{{% tab tabNum="1" %}}
``` md
---
title: "Quick Start"
icon: "icon-layers"
type : "category"
weight: 1
---
```
{{% /tab %}}

{{% tab tabNum="2" %}}
``` md
---
title: "Initialize Hugo"
weight: 1
draft: false
lastmod: 2020-11-5
type: docs
layout: two-col
---

...
```
{{% /tab %}}
{{< /tabs >}}
{{</code/float-window>}}

{row-divider}
#### Testing it out
That's it, you can start writing pages in markdown and see them updated in real time!

{{<code/code-block>}}
{{< figure src="/docs/quick-start/empty.png" title="" width="">}}
{{</code/code-block>}}

{divider}
{{%code/code-block%}}
```bash 
hugo serve

# if you want to include drafts

hugo serve -D
```
{{%/code/code-block%}}

{row-divider}
#### Build it
That's it, you can start writing pages in markdown and see them updated in real time!
{divider}
{{%code/code-block%}}
```bash 
hugo

# if you want to include drafts

hugo -D
```
{{%/code/code-block%}}
