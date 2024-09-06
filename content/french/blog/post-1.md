---
title: "How to build an Application with modern Technology"
meta_title: ""
description: "this is meta description"
date: 2022-04-04T05:00:00Z
image: ""
categories: ["Application", "Data"]
author: "John Doe"
tags: ["nextjs", "tailwind","tailwind","tailwind","tailwind","tailwind","tailwind","tailwind","tailwind","tailwind",]
draft: false
table_of_contents: true
mermaid: true
vegalite: true
featured: true
---

Salaut ceci est texte d'exemple de résumé pour vérifier la longueur ou non ca marche.


## Création de la clé
eee
### sous création de clé
ouiuiu

{{< mermaid >}}
flowchart LR
    y("👫 You") --> h{"🤝 Found this helpful?"}
    h --> |Yes| t[eee]
    h --> |No| su[eee]
    click r "/categories/featured" _blank
{{< /mermaid >}}


{{< mermaid >}}
quadrantChart
    title Reach and engagement of campaigns
    x-axis Low Reach --> High Reach
    y-axis Low Engagement --> High Engagement
    quadrant-1 We should expand
    quadrant-2 Need to promote
    quadrant-3 Re-evaluate
    quadrant-4 May be improved
    Campaign A: [0.3, 0.6]
    Campaign B: [0.45, 0.23]
    Campaign C: [0.57, 0.69]
    Campaign D: [0.78, 0.34]
    Campaign E: [0.40, 0.34]
    Campaign F: [0.35, 0.78]
{{< /mermaid >}}


{{< vegalite id="monGraphique" >}}
{
  "$schema": "https://vega.github.io/schema/vega-lite/v5.json",
  "width": "container",
  "description": "Un simple graphique à barres.",
  "data": {
    "values": [
      {"category": "A", "value": 28},
      {"category": "B", "value": 55},
      {"category": "C", "value": 43},
      {"category": "D", "value": 91},
      {"category": "E", "value": 81},
      {"category": "F", "value": 53},
      {"category": "G", "value": 19},
      {"category": "H", "value": 87}
    ]
  },
  "mark": {
    "type": "bar",
    "tooltip": true
  },
  "encoding": {
    "x": {"field": "category", "type": "nominal", "axis": {"labelAngle": 0}},
    "y": {"field": "value", "type": "quantitative"},
    "tooltip": [{"field": "value", "type": "quantitative", "title": "Valeur"}]
  }
}
{{< /vegalite >}}


Encore un gaaoh

{{< vegalite id="graph2" >}}
{
  "$schema": "https://vega.github.io/schema/vega-lite/v5.json",
  "width": "container",
  "description": "Un simple graphique à barres.",
  "data": {
    "values": [
      {"category": "A", "value": 28},
      {"category": "B", "value": 55},
      {"category": "C", "value": 43},
      {"category": "D", "value": 91},
      {"category": "E", "value": 81}
    ]
  },
  "mark": {
    "type": "bar",
    "tooltip": true
  },
  "encoding": {
    "x": {"field": "category", "type": "nominal", "axis": {"labelAngle": 0}},
    "y": {"field": "value", "type": "quantitative"},
    "tooltip": [{"field": "value", "type": "quantitative", "title": "Valeur"}]
  }
}
{{< /vegalite >}}


{{< vegalite id="graph3" >}}
{
  "$schema": "https://vega.github.io/schema/vega-lite/v5.json",
  "width": "container",
  "description": "Un simple graphique à barres.",
  "data": {
    "values": [
      {"category": "A", "value": 28},
      {"category": "B", "value": 55},
      {"category": "C", "value": 43},
      {"category": "D", "value": 91},
      {"category": "E", "value": 81},
      {"category": "F", "value": 53}
    ]
  },
  "mark": {
    "type": "bar",
    "tooltip": true
  },
  "encoding": {
    "x": {"field": "category", "type": "nominal", "axis": {"labelAngle": 0}},
    "y": {"field": "value", "type": "quantitative"},
    "tooltip": [{"field": "value", "type": "quantitative", "title": "Valeur"}]
  }
}
{{< /vegalite >}}



## titre 2
Essai `ee`

```text
sequenceDiagram
    participant Alice
    participant Bob
    Alice->>John: Hello John, how are you?
    loop Healthcheck
        John->>John: Fight against hypochondria
    end
    Note right of John: Rational thoughts <br/>prevail!
    John-->>Alice: Great!
    John->>Bob: How about you?
    Bob-->>John: Jolly good!
```





### Titre 3

#### Titre 3

## Titre 2.1

## Creative Design

Nam ut rutrum ex, venenatis sollicitudin urna. Aliquam erat volutpat. Integer eu ipsum sem. Ut bibendum lacus vestibulum maximus suscipit. Quisque vitae nibh iaculis neque blandit euismod.

> Lorem ipsum dolor sit amet consectetur adipisicing elit. Nemo vel ad consectetur ut aperiam. Itaque eligendi natus aperiam? Excepturi repellendus consequatur quibusdam optio expedita praesentium est adipisci dolorem ut eius!

Lorem ipsum dolor sit amet consectetur adipisicing elit. Nemo vel ad consectetur ut aperiam. Itaque eligendi natus aperiam? Excepturi repellendus consequatur quibusdam optio expedita praesentium est adipisci dolorem ut eius!


{{< highlight go-html-template >}}
{{ range .Pages }}
  <h2><a href="{{ .RelPermalink }}">{{ .LinkTitle }}</a></h2>
{{ end }}
{{< /highlight >}}

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