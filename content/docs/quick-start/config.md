---
title: "Configuration"
weight: 2
draft: false
lastmod: 2020-11-5
# search related keywords
type: docs
layout: two-col
---
{row-divider}
#### Color pallet
Clyde is themable, you can make clyde match the color scheme of your projects easily. These parameters can be modified under `config.toml`
{divider}
``` toml
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
```

{row-divider}
#### Logos
Clyde allows you to use square logos for your site. It will appear on the top of the sidebar menu, when the menu auto collapses, you can reopen it using the logo as a button.   

You can also just use a red circle provided by Clyde, it's not very pretty though.
{divider}
``` toml
#red circle
[params]
    logo = "/default_button.png"
```

{row-divider}
#### Top nav links
Clyde allows you to add nav links on the top bar. Clyde suggests you use these for external links, or links to parts of your app outside the `/docs` folder. This is for better UX design consistency.

You can order them using the `weight` parameter and add icons through the `pre` parameter. (We use [feather icons](https://feathericons.com/))

The `url` can be relative to the app, or absolute. 

{divider}
``` toml
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