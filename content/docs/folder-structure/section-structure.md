---
title: "Section Structure"
weight: 2
draft: false
lastmod: 2020-11-5
type: docs
layout: two-col
---
{row-divider}
#### Base URL
The base URL has 2 components.
1. `http://example.org/` is a generic domain place holder, this shows Hugo where the base domain begins and ends
2. `clyde-example-app/` this is where you specify the root route of your app. All relative urls will resolve to `clyde-example-app/<hugo routing>/...`
{divider}
``` toml
baseURL = "http://example.org/clyde-example-app/"
```

