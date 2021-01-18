---
title: "Tabs"
weight: 2
draft: false
lastmod: 2020-11-5
type: docs
layout: two-col
---
{row-divider}
#### Tabs
You've seen these things, they're the centerpiece of Clyde's aesthetics. 

The following example is derived from [GA4GH Discovery Docs](https://github.com/ga4gh-discovery/ga4gh-search/), which is written using Clyde.
{divider}
{{<code/float-window>}}
{{< tabs tabTotal="2" tabID="float" tabName1="Example #1" tabName2="Example #2">}}
{{% tab tabNum="1" %}}
This query returns all female patients from the `patient` table.
``` SQL
/* you can scroll on this tab */
SELECT * 
FROM   kidsfirst.ga4gh_tables.patient 
WHERE  Json_extract_scalar(patient, '$.gender') = 'female' 
LIMIT  5; 
```
{{% /tab %}}

{{% tab tabNum="2" %}}

This query returns all conditions observed in female patients from the `patient` table.
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
{row-divider}
#### Using tabs
A few key details to note
- `tabTotal` defines number of tabs defined
- `tabID` should be **unique** for the page, this is the reference to trigger navigation switching
- `tabName1` through `tabNameX` are the names displayed on the navigation buttons
- The inner tags should use `% %` tag over `< >` to render inner markdown properly
- `tabNum="X"` should match its tab name number

{divider}
``` markdown
{{</* tabs tabTotal="2" tabID="float2" tabName1="Example #1" tabName2="Example #2" */>}}
{{%/* tab tabNum="1" */%}}
    content1 
{{%/* /tab */%}}

{{%/* tab tabNum="2" */%}}
    content2
{{%/* /tab */%}}
{{</* /tabs */>}}
```
