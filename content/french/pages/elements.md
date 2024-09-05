---
title: "Sample"
# meta title
meta_title: ""
# meta description
description: "This is meta description"
# save as draft
draft: false
mermaid: true
vegalite: true
---

{{< toc >}}

Here is an example of headings. You can use this heading by the following markdown rules. For example: use `#` for heading 1 and use `######` for heading 6.

# Heading 1

## Heading 2

### Heading 3

#### Heading 4

##### Heading 5

###### Heading 6

<hr>

### Emphasis

The emphasis, aka italics, with _asterisks_ or _underscores_.

Strong emphasis, aka bold, with **asterisks** or **underscores**.

The combined emphasis with **asterisks and _underscores_**.

Strike through uses two tildes. ~~Scratch this.~~

<hr>

### Button

{{< button label="Button" link="/" style="solid" >}}

<hr>

### Link

[I'm an inline-style link](https://www.google.com)

[I'm an inline-style link with title](https://www.google.com "Google's Homepage")

[I'm a reference-style link][Arbitrary case-insensitive reference text]

[I'm a relative reference to a repository file](../blob/master/LICENSE)

[You can use numbers for reference-style link definitions][1]

Or leave it empty and use the [link text itself].

URLs and URLs in angle brackets will automatically get turned into links.
<http://www.example.com> or <http://www.example.com> and sometimes
example.com (but not on Github, for example).

Some text to show that the reference links can follow later.

[arbitrary case-insensitive reference text]: https://www.themefisher.com
[1]: https://gethugothemes.com
[link text itself]: https://www.getjekyllthemes.com

<hr>

### Paragraph

Lorem ipsum dolor sit amet consectetur adipisicing elit. Quam nihil enim maxime corporis cumque totam aliquid nam sint inventore optio modi neque laborum officiis necessitatibus, facilis placeat pariatur! Voluptatem, sed harum pariatur adipisci voluptates voluptatum cumque, porro sint minima similique magni perferendis fuga! Optio vel ipsum excepturi tempore reiciendis id quidem? Vel in, doloribus debitis nesciunt fugit sequi magnam accusantium modi neque quis, vitae velit, pariatur harum autem a! Velit impedit atque maiores animi possimus asperiores natus repellendus excepturi sint architecto eligendi non, omnis nihil. Facilis, doloremque illum. Fugit optio laborum minus debitis natus illo perspiciatis corporis voluptatum rerum laboriosam.

<hr>

### Ordered List

1. List item
2. List item
3. List item
4. List item
5. List item

<hr>

### Unordered List

- List item
- List item
- List item
- List item
- List item

<hr>

### Notice

{{< notice "note" >}}
This is a simple note.
{{< /notice >}}

{{< notice "tip" >}}
This is a simple tip.
{{< /notice >}}

{{< notice "info" >}}
This is a simple info.
{{< /notice >}}

{{< notice "warning" >}}
This is a simple warning.
{{< /notice >}}

<hr>

### Tab

{{< tabs >}}
{{< tab "Tab 1" >}}

#### Did you come here for something in particular?

Did you come here for something in particular or just general Riker-bashing? And blowing into maximum warp speed, you appeared for an instant to be in two places at once. We have a saboteur aboard. We know you’re dealing in stolen ore. But I wanna talk about the assassination attempt on Lieutenant Worf.

{{< /tab >}}

{{< tab "Tab 2" >}}

#### I wanna talk about the assassination attempt

Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet.

Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet.

{{< /tab >}}

{{< tab "Tab 3" >}}

#### We know you’re dealing in stolen ore

Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet.

Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo

{{< /tab >}}
{{< /tabs >}}

<hr>

### Accordions

{{< accordion "Why should you need to do this?" >}}

- Lorem ipsum dolor sit amet consectetur adipisicing elit.
- Lorem ipsum dolor sit amet consectetur adipisicing elit.
- Lorem ipsum dolor sit amet consectetur

{{< /accordion >}}

{{< accordion "How can I adjust Horizontal centering" >}}

- Lorem ipsum dolor sit amet consectetur adipisicing elit.
- Lorem ipsum dolor sit amet consectetur adipisicing elit.
- Lorem ipsum dolor sit amet consectetur

{{< /accordion >}}

{{< accordion "Should you use Negative margin?" >}}

- Lorem ipsum dolor sit amet consectetur adipisicing elit.
- Lorem ipsum dolor sit amet consectetur adipisicing elit.
- Lorem ipsum dolor sit amet consectetur

{{< /accordion >}}

<hr>

### Code and Syntax Highlighting

This is an `Inline code` sample.

```python
s = "Python syntax highlighting"
print s
```
Test with shortcode.
{{< highlight go-html-template >}}
{{ range .Pages }}
  <h2><a href="{{ .RelPermalink }}">{{ .LinkTitle }}</a></h2>
{{ end }}
{{< /highlight >}}


<hr>

### Mermaid
Use memraid with shortcode.
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


### Vega-lite
Generate charts whith Vega-Lite.
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


{{< vegalite id="graphcomplex" >}}
{
  "$schema": "https://vega.github.io/schema/vega/v5.json",
  "width": "600",
  "height": 500,
  "padding": 5,
  "title": {
    "text": "Seattle Annual Temperatures",
    "anchor": "middle",
    "fontSize": 16,
    "frame": "group",
    "offset": 4
  },
  "data": [
    {
      "name": "temperature",
      "url": "https://vega.github.io/vega/data/seattle-weather-hourly-normals.csv",
      "format": {
        "type": "csv",
        "parse": {"temperature": "number", "date": "date"}
      },
      "transform": [
        {"type": "formula", "as": "hour", "expr": "hours(datum.date)"},
        {
          "type": "formula",
          "as": "day",
          "expr": "datetime(year(datum.date), month(datum.date), date(datum.date))"
        }
      ]
    }
  ],
  "scales": [
    {
      "name": "x",
      "type": "time",
      "domain": {"data": "temperature", "field": "day"},
      "range": "width"
    },
    {
      "name": "y",
      "type": "band",
      "domain": [
        6,
        7,
        8,
        9,
        10,
        11,
        12,
        13,
        14,
        15,
        16,
        17,
        18,
        19,
        20,
        21,
        22,
        23,
        0,
        1,
        2,
        3,
        4,
        5
      ],
      "range": "height"
    },
    {
      "name": "color",
      "type": "linear",
      "range": {"scheme": "redyellowblue"},
      "domain": {"data": "temperature", "field": "temperature"},
      "reverse": true,
      "zero": false,
      "nice": true
    }
  ],
  "axes": [
    {
      "orient": "bottom",
      "scale": "x",
      "domain": false,
      "title": "Month",
      "format": "%b"
    },
    {
      "orient": "left",
      "scale": "y",
      "domain": false,
      "title": "Hour",
      "encode": {
        "labels": {
          "update": {
            "text": {
              "signal": "datum.value === 0 ? 'Midnight' : datum.value === 12 ? 'Noon' : datum.value < 12 ? datum.value + ':00 am' : (datum.value - 12) + ':00 pm'"
            }
          }
        }
      }
    }
  ],
  "legends": [
    {
      "fill": "color",
      "type": "gradient",
      "title": "Avg. Temp (°F)",
      "titleFontSize": 12,
      "titlePadding": 4,
      "gradientLength": {"signal": "height - 16"}
    }
  ],
  "marks": [
    {
      "type": "rect",
      "from": {"data": "temperature"},
      "encode": {
        "enter": {
          "x": {"scale": "x", "field": "day"},
          "y": {"scale": "y", "field": "hour"},
          "width": {"value": 5},
          "height": {"scale": "y", "band": 1},
          "tooltip": {
            "signal": "timeFormat(datum.date, '%b %d %I:00 %p') + ': ' + datum.temperature + '°'"
          }
        },
        "update": {"fill": {"scale": "color", "field": "temperature"}}
      }
    }
  ]
}
{{< /vegalite >}}

### Blockquote

> Did you come here for something in particular or just general Riker-bashing? And blowing into maximum warp speed, you appeared for an instant to be in two places at once.

<hr>

### Tables

| Tables        |      Are      |  Cool |
| ------------- | :-----------: | ----: |
| col 3 is      | right-aligned | $1600 |
| col 2 is      |   centered    |   $12 |
| zebra stripes |   are neat    |    $1 |

<hr>

### Image

{{< image src="images/image-placeholder.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title="image title"  webp="false" >}}

<hr>

### Gallery

{{< gallery dir="images/gallery" class="" height="400" width="400" webp="true" command="Fit" option="" zoomable="true" >}}

<hr>

### Slider

{{< slider dir="images/gallery" class="max-w-[600px] ml-0" height="400" width="400" webp="true" command="Fit" option="" zoomable="true" >}}

<hr>

