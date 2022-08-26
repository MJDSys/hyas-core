# Hyas core

Core templates for Hyas sites.

## Status

[![npm (scoped)](https://img.shields.io/npm/v/@hyas/core?style=flat-square)](https://www.npmjs.com/package/@hyas/core) [![GitHub Workflow Status](https://img.shields.io/github/workflow/status/h-enk/hyas-core/CodeQL?style=flat-square)]((https://github.com/h-enk/hyas-core/actions/workflows/codeql.yml))

## Requirements

- [@hyas/seo](https://www.npmjs.com/package/@hyas/seo)

## Installation

```bash
npm i @hyas/core -D
```

## Setup

Add to `./config/_default/module.toml`:

```toml
[[mounts]]
  source = "node_modules/@hyas/core/assets"
  target = "assets"

[[mounts]]
  source = "node_modules/@hyas/core/layouts"
  target = "layouts"

[[mounts]]
  source = "assets"
  target = "assets"

[[mounts]]
  source = "layouts"
  target = "layouts"
```

Add to `./config/_default/config.toml`:

```toml
baseurl = "https://hyas.netlify.app/"
canonifyURLs = false
disableAliases = true
disableHugoGeneratorInject = true
disableKinds = ["taxonomy", "term"]
enableEmoji = true
enableGitInfo = false
enableRobotsTXT = true
languageCode = "en-US"
paginate = 7
rssLimit = 10

[outputs]
  home = ["HTML", "RSS"]

[caches]
  [caches.getjson]
    dir = ":cacheDir/:project"
    maxAge = "10s"

[sitemap]
  changefreq = "monthly"
  filename = "sitemap.xml"
  priority = 0.5

[minify.tdewolff.html]
  keepWhitespace = false
```

Add to `./config/_default/params.toml`:

```toml
## Chrome Browser
themeColor = "#fff"

# Feed
copyRight = "Copyright (c) 2020-2021 Henk Verlinde"
```

## Usage

See the Hyas docs: [Quick Start](https://gethyas.com/docs/prologue/quick-start/)