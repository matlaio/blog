---
title: "How to build an Application with modern Technology"
meta_title: ""
description: "this is meta description"
date: 2022-04-04T05:00:00Z
image: "/images/image-placeholder.png"
categories: ["Application", "Data"]
author: "John Doe"
tags: ["nextjs", "tailwind","tailwind","tailwind","tailwind","tailwind","tailwind","tailwind","tailwind","tailwind",]
draft: false
---

Lorem  l'a L'a ipsum dolor sit amet, consectetur adipiscing elit. Sed non risus. Suspendisse lectus tortor, dignissim sit amet, adipiscing nec, ultricies sed, dolor. Cras elementum ultrices diam. Maecenas ligula massa, varius a, semper congue, euismod non, mi. Proin porttitor, orci nec nonummy molestie, enim est eleifend mi, non fermentum diam nisl sit amet erat. Duis semper. Duis arcu massa, scelerisque vitae, consequat in, pretium a, enim. Pellentesque congue. Ut in risus volutpat libero pharetra tempor. Cras vestibulum bibendum augue. Praesent egestas leo in pede. Praesent blandit odio eu enim. Pellentesque sed dui ut augue blandit sodales. Vestibulum ante ipsum primis in faucibus orci luctus et ultrices posuere cubilia Curae; Aliquam nibh. Mauris ac mauris sed pede pellentesque fermentum. Maecenas adipiscing ante non diam sodales hendrerit. 

## titre 2
eee

### Titre 3

#### Titre 3

## Titre 2.1

## Creative Design

Nam ut rutrum ex, venenatis sollicitudin urna. Aliquam erat volutpat. Integer eu ipsum sem. Ut bibendum lacus vestibulum maximus suscipit. Quisque vitae nibh iaculis neque blandit euismod.

> Lorem ipsum dolor sit amet consectetur adipisicing elit. Nemo vel ad consectetur ut aperiam. Itaque eligendi natus aperiam? Excepturi repellendus consequatur quibusdam optio expedita praesentium est adipisci dolorem ut eius!

Lorem ipsum dolor sit amet consectetur adipisicing elit. Nemo vel ad consectetur ut aperiam. Itaque eligendi natus aperiam? Excepturi repellendus consequatur quibusdam optio expedita praesentium est adipisci dolorem ut eius!

```js
function HelloWorld({
  greeting = "hello",
  greeted = '"World"',
  silent = false,
  onMouseOver,
}) {
  if (!greeting) {
    return null;
  }

  // TODO: Don't use random in render
  let num = Math.floor(Math.random() * 1e7)
    .toString()
    .replace(/\.\d+/gi, "");

  return (
    <div
      className="HelloWorld"
      title={`You are visitor number ${num}`}
      onMouseOver={onMouseOver}>
      <strong>
        {greeting.slice(0, 1).toUpperCase() + greeting.slice(1).toLowerCase()}
      </strong>
      {greeting.endsWith(",") ? " " : <span style={{color: "grey"}}>", "</span>}
      <em>{greeted}</em>
      {silent ? "." : "!"}
    </div>
  );
}

```

Example de code inline `yetttt`.

```bash
PS C:\Users\mat> news-scraper-pdf.exe --help
usage: news-scraper-pdf [-h] [-e ENV] [-f FIRST_PAGES] [-v] [-n NEXTCLOUD_PATH] [-o OUTPUT_PATH] source razr rzer rzer zerze rez rezrez rez r

positional arguments:
  source                Source of media to find latest publication.

options:
  -h, --help            show this help message and exit
  -e ENV, --env ENV     Specifie env mode. By default taking file refrenced in os variable ENV_NEWS_SCRAPER.
  -f FIRST_PAGES, --first-pages FIRST_PAGES
                        Get the first N pages.
  -v, --verbose         Enable verbose mode.
  -n NEXTCLOUD_PATH, --nextcloud-path NEXTCLOUD_PATH
                        Set Nextcloud upload directory path. Need to configure valid connection with --env
  -o OUTPUT_PATH, --output-path OUTPUT_PATH
                        Write file to a specific path.
```