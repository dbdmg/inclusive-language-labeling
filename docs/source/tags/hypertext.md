---
title: HyperText
type: tags
order: 303
meta_title: Hypertext Tags for Hypertext Markup (HTML)
meta_description: Label Studio Hypertext Tags customize Label Studio for hypertext markup (HTML) for machine learning and data science projects.
---

HyperText tag shows HyperText markup that can be labeled.

### Parameters

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| name | <code>string</code> |  | Name of the element |
| value | <code>string</code> |  | Value of the element |
| [valueType] | <code>url</code> \| <code>text</code> |  | Where the text is stored — directly in uploaded data or needs to be loaded from a URL |
| [saveTextResult] | <code>yes</code> \| <code>no</code> |  | Whether or not to store labeled text along with the results. By default doesn't store text for `valueType=url` |
| [showLabels] | <code>boolean</code> | <code>false</code> | Whether to show labels next to the region |
| [encoding] | <code>none</code> \| <code>base64</code> \| <code>base64unicode</code> |  | How to decode values from encoded strings |
| [clickableLinks] | <code>boolean</code> | <code>false</code> | Whether to allow opening resources from links in the hypertext markup. |

### Sample Results JSON

| Name | Type | Description |
| --- | --- | --- |
| value | <code>Object</code> |  |
| value.start | <code>string</code> | xpath of the container where the region starts (xpath) |
| value.end | <code>string</code> | xpath of the container where the region ends (xpath) |
| value.startOffset | <code>number</code> | offset within start container |
| value.endOffset | <code>number</code> | offset within end container |
| [value.text] | <code>string</code> | text content of the region, can be skipped |

### Example JSON
```json
{
  "value": {
    "start": "/div[1]/p[2]/text()[1]",
    "end": "/div[1]/p[4]/text()[3]",
    "startOffset": 2,
    "endOffset": 81,
    "hypertextlabels": ["Car"]
  }
}
```

### Example
```html
<View>
  <HyperText name="text-1" value="$text" />
  <Labels name="parts" toName="text-1">
    <Label value="Caption" />
    <Label value="Article" />
    <Label value="Author" />
  </Labels>
</View>
```
