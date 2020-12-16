---
title: "Section Structure"
weight: 2
draft: false
lastmod: 2020-11-5
type: docs
layout: two-col
---
{row-divider}
#### What are sections?
Each subfolder under `content` is a section, for example: `content/docs`. Each section has its unique, auto generated sidebar menu. We keep these sections 2 layers deep, with a structure of `type: category`/`type: docs`. 
{divider}
```
content
    └── docs
        ├── folder-structure
        │   ├── _index.md
        │   ├── project-structure.md
        │   └── section-structure.md
        ├── layout
        │   ├── _index.md
        │   ├── single.md
        │   └── two-col.md
        ├── quick-start
        │   ├── _index.md
        │   ├── config.md
        │   └── init.md
        └── short-code
            ├── _index.md
            └── two-col.md
```
{row-divider}
#### How the sidebar menu works
Notice the `_index.md` file in each folder under the `docs` section? They specify how the `category` represented by each folder is rendered at the side bar.

The example provided is the `Folder Structure` category. 

`title: "Folder Structure"` specifies the name of the side bar item.
`icon: "icon-folder"` specifies icon name (we use feather icons).
`type : "category"` specifies that this file is rendered as a category 
`weight: 2` is used to order the menu items, from 1 onwards

The files, like `section-structure.md` have `type: docs` specified in the front matter. These are the subitems of each category.
`title: "Folder Structure"` specifies the name of the side bar item.
`draft: "false"` is used to mark drafts, so they're ignored during builds
`type : "docs"` specifies that this file is rendered as a document item
`weight: 2` is used to order the menu items, from 1 onwards
`layout: two-col` specifies the layout

{divider}
{{<code/float-window>}}
{{< tabs tabTotal="2" tabID="1" tabName1="_index.md" tabName2="section-structure.md">}}
{{% tab tabNum="1" %}}
``` md
---
title: "Folder Structure"
icon: "icon-folder"
type : "category"
weight: 2
---
```
{{% /tab %}}
{{% tab tabNum="2" %}}
```md
---
title: "Section Structure"
weight: 2
draft: false
lastmod: 2020-11-5
type: docs
layout: two-col
---
```
{{% /tab %}}
{{< /tabs >}}
{{</code/float-window>}}
