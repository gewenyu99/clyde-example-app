---
title: "Project Structure"
weight: 1
draft: false
lastmod: 2020-11-5
type: docs
layout: two-col
---
{row-divider}
#### Base Structure
Take a look at the base file structure, we'll talk about what each folder does through this section.
###### Content
The `content` folder is where your content lives. The subfolders like `docs` and `api` define subroutes under the site, which will index unique sidebar menu items (we'll talk more about the sidebar later).
###### Static
The static folder is where I recommend you keep stuff like images and other non-markdown material here. The static folder's content is served directly under the base url. For example `static/image.png` maps to `http://baseurl.com/image.png`. This can be then referenced with markdown.
###### Themes/clyde
This is where clyde lives. We'll talk about clyde in its own section.

{divider}
{{<code/float-window>}}
{{< tabs tabTotal="1" tabID="1" tabName1="File Structure">}}
{{% tab tabNum="1" %}}
``` bash
.
├── archetypes
├── content
│   └── docs -> http://baseurl.com/api
│       ├── category -> http://baseurl.com/api/subsection
│       └── ...
│   └── api -> http://baseurl.com/api
│       └── ...
├── data
├── layouts
├── static
└── themes
    └── clyde
        ├── archetypes
        ├── layouts
        │   ├── _default
        │   ├── docs
        │   ├── partials
        │   │   └── page-layouts
        │   └── shortcodes
        │       └── code
        └── static
            ├── css
            │   ├── page-layouts
            │   ├── sidebar
            │   └── tabs
            ├── feather-icons
            │   ├── css
            │   ├── fonts
            │   └── icons
            └── js
```
{{% /tab %}}
{{< /tabs >}}
{{</code/float-window>}}
