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
This page will cover the basics of configuring Clyde.

#### Base URL
The base URL has 2 components.
1. `http://example.org/` is a generic domain place holder, this shows Hugo where the base domain begins and ends
2. `clyde-example-app/` this is where you specify the root route of your app. All relative urls will resolve to `clyde-example-app/<hugo routing>/...`. This is used when deploying to Github pages.
{divider}
``` toml
baseURL = "http://example.org/clyde-example-app/"
```
{row-divider}
#### Basic Information
`title` specifies the displayed name of your site

`theme` specifies theme used, which is `clyde` in this case.

`pygmentsUseClasses` allows us to customize code highlight colors

`publishDir` specifies which folder into which Clyde compiles the built site.

`relativeURLs` and `canonifyURLs` are specified to make Clyde's sidebar menu work properly. Don't worry about these, keep them on `true`.
{divider}
``` toml
title = "Clyde Sample App"
theme = "clyde"
pygmentsUseClasses=true
publishDir = "docs"
relativeURLs = true
canonifyURLs = true
```
{row-divider}
#### Color pallet
Clyde is themable, you can make clyde match the color scheme of your projects easily. These parameters can be modified under `config.toml`.
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
{divider}
``` scss
// These are the defined colors available for configuration
// Not all are used by default, but you can use these for custom theming of Clyde components.
--white: #ffffff;
--primary: {{ .Site.Params.primary }};
--secondary: {{ .Site.Params.secondary }};
--sidebar-bg: {{ .Site.Params.sidebar_bg }};
--sidebar-primary: {{ .Site.Params.sidebar_primary }};
--accent: {{ .Site.Params.accent }};
--grey100: {{ .Site.Params.grey100 }};
--grey200: {{ .Site.Params.grey200 }};
--grey300: {{ .Site.Params.grey300 }};
--grey400: {{ .Site.Params.grey400 }};
--grey500: {{ .Site.Params.grey500 }};
--grey600: {{ .Site.Params.grey600 }};
--grey700: {{ .Site.Params.grey700 }};
--grey800: {{ .Site.Params.grey800 }};
--grey900: {{ .Site.Params.grey900 }};
--grey-head: {{ .Site.Params.grey_head }};
--nav-highlight: {{ .Site.Params.nav_highlight }};
```

{row-divider}
#### Logos
Clyde allows you to use square logos for your site. It will appear on the top of the sidebar menu, when the menu auto collapses, you can reopen it using the logo as a button.   

You can also just use Clyde's default icon, it's not very pretty though.
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