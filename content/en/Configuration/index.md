---
title: Configure NavCoin
linktitle: Configure NavCoin
description: How to configure NavCoin Core with a configuration file.
date: 2013-07-01
publishdate: 2017-01-02
lastmod: 2017-03-05
categories: [fundamentals]
keywords: [configuration]
weight: 60
sections_weight: 60
draft: false
toc: true
---

NavCoin uses the `config.toml`, `config.yaml`, or `config.json` (if found in the
site root) as the default site config file.

The user can choose to override that default with one or more site config files
using the command line `--config` switch.

Examples:

```
hugo --config debugconfig.toml
hugo --config a.toml,b.toml,c.toml
```

{{% note %}}
Alternate config files can be specified as a [launch option](/launch-options) using the `--placeholder what is the command` switch.
{{% /note %}}

## All Configuration Settings

The following is the full list of NavCoin-defined variables with their default
value in parentheses. Users may choose to override those values in their site
config file(s).


{{% note %}}
If you are developing your site on a \*nix machine, here is a handy shortcut for finding a configuration option from the command line:
```
cd ~/sites/yourhugosite
hugo config | grep emoji
```

which shows output like

```
enableemoji: true
```
{{% /note %}}

## Configuration Lookup Order

Similar to the template [lookup order][], NavCoin has a default set of rules for searching for a configuration file in the root of your website's source directory as a default behavior:

1. `./config.toml`
2. `./config.yaml`
3. `./config.json`

In your `config` file, you can direct NavCoin as to how you want your website rendered, control your website's menus, and arbitrarily define site-wide parameters specific to your project.


## Example Configuration

The following is a typical example of a configuration file. The values nested under `params:` will populate the [`.Site.Params`][] variable for use in [templates][]:

{{< code-toggle file="config">}}
baseURL: "https://yoursite.example.com/"
title: "My NavCoin Site"
footnoteReturnLinkContents: "↩"
permalinks:
  post: /:year/:month/:title/
params:
  Subtitle: "NavCoin is Absurdly Fast!"
  AuthorName: "Jon Doe"
  GitHubUser: "spf13"
  ListOfFoo:
    - "foo1"
    - "foo2"
  SidebarRecentLimit: 5
{{< /code-toggle >}}

