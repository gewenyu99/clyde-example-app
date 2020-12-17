---
title: "Shortcode"
weight: 1
draft: false
lastmod: 2020-11-5
type: docs
layout: two-col
---
{row-divider}
#
#### Introduction
Short codes are used as markdown inserts. They allow us to use custom rendering logic to render code blocks, floating tab windows, videos, images, and many other cool things!
{divider}
{{<code/float-window>}}
{{%content-textbox%}}
##### Quick Links
---
[Hugo Shortcodes](https://gohugo.io/content-management/shortcodes/)
{{%/content-textbox%}}
{{</code/float-window>}}
{row-divider}
#### A note about render logic
Shortcode can render its inners as markdown, or plain text.

Use this when nesting shortcode, or when you need to display markdown that doesn't need to be rendered.
{divider}
{{<code/float-window>}}
{{< tabs tabTotal="2" tabID="float" tabName1="Not Rendered" tabName2="Rendered">}}
{{< tab tabNum="1" >}}
this isn't rendered
``` SQL
/* you can scroll on this tab */
SELECT * 
FROM   kidsfirst.ga4gh_tables.patient 
WHERE  Json_extract_scalar(patient, '$.gender') = 'female' 
LIMIT  5; 
```
{{< /tab >}}

{{% tab tabNum="2" %}}
This is rendered
``` SQL
/* you can scroll on this tab */
SELECT Json_extract_scalar(ncpi_disease, '$.code.text')           AS disease, 
       Json_extract_scalar(ncpi_disease, '$.identifier[0].value') AS identifier 
FROM   kidsfirst.ga4gh_tables.ncpi_disease disease 
       INNER JOIN kidsfirst.ga4gh_tables.patient patient 
               ON patient.id = REPLACE(Json_extract_scalar(ncpi_disease, 
                                       '$.subject.reference'), 
                               'Patient/') 
WHERE  Json_extract_scalar(patient, '$.gender') = 'female' 
LIMIT  5; 
```
{{% /tab %}}
{{< /tabs >}}
{{</code/float-window>}}
