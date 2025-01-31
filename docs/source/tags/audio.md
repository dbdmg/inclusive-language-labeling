---
title: Audio
type: tags
order: 301
meta_title: Audio Tags for Labeling Audio
meta_description: Label Studio Audio Tags customize Label Studio for labeling audio for machine learning and data science projects.
---

Audio tag plays a simple audio file.

### Parameters

| Param | Type | Description |
| --- | --- | --- |
| name | <code>string</code> | Name of the element |
| value | <code>string</code> | Value of the element |
| hotkey | <code>string</code> | Hotkey used to play or pause audio |

### Sample Results JSON

| Name | Type | Description |
| --- | --- | --- |
| original_length | <code>number</code> | length of the original audio (seconds) |
| value | <code>Object</code> |  |
| value.start | <code>number</code> | start time of the fragment (seconds) |
| value.end | <code>number</code> | end time of the fragment (seconds) |

### Example JSON
```json
{
  "original_length": 18,
  "value": {
    "start": 3.1,
    "end": 8.2,
    "labels": ["Voice"]
  }
}
```

### Example
```html
<View>
  <Audio name="audio" value="$audio" />
</View>
```
### Example

Audio classification

```html
<View>
  <Audio name="audio" value="$audio" />
  <Choices name="ch" toName="audio">
    <Choice value="Positive" />
    <Choice value="Negative" />
  </Choices>
</View>
```
### Example

Audio transcription

```html
<View>
  <Audio name="audio" value="$audio" />
  <TextArea name="ta" toName="audio" />
</View>
```
