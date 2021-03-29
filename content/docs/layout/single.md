---
title: "Single Column"
weight: 1
draft: false
lastmod: 2020-11-5
type: docs
layout: single-col
---
This page is a single column page! 

It's just standard Markdown

{{< tabs tabTotal="3" tabID="2" tabName1="Python" tabName2="R" tabName3="CLI">}}
{{% tab tabNum="1" %}}
``` Python
print("Clyde is a name!")
```
{{% /tab %}}
{{% tab tabNum="2" %}}
``` R
print("Clyde is a name!")
```
{{% /tab %}}
{{% tab tabNum="3" %}}
{{<content-textbox>}}
Clyde dislikes commandline interfaces.
{{</content-textbox>}}
{{% /tab %}}

{{< /tabs >}}

Everything is just in a single column, just specify `layout: single-col` in the frontmatter.

{{%code/code-block%}}
``` md
---
title: "Single Column"
weight: 1
draft: false
lastmod: 2020-11-5
type: docs
layout: single-col
---
```
{{%/code/code-block%}}
