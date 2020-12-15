---
title: "Two Column"
weight: 1
draft: false
lastmod: 2020-11-5
type: docs
layout: two-col
---
{row-divider}
This page is in two columns! 

It's just standard Markdown with a minor addition.

You'll need to add a `{` `row-divider` `}` in markdown to indicate a new row of content.

You'll need to add a `{` `divider` `}` in markdown to indicate where to split the row.

Clyde will only display content that is properly formatted like this.

If Clyde feels the window is to narrow, it will wrap the page responsively into a single column.

***Check the source code of this page to see the details. Clyde is a man of habbit, he will render the divider tags if I include them in this page.***


{{< figure src="/default_button.png" title="Rules are rules man - Clyde 2020" width="500rem">}}

{divider}
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
