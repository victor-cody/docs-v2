---
title: strings.index() function
description: >
  `strings.index()` returns the index of the first instance of a substring in a string.
  If the substring is not present, it returns `-1`.
menu:
  flux_0_x_ref:
    name: strings.index
    parent: strings
    identifier: strings/index
weight: 101
---

<!------------------------------------------------------------------------------

IMPORTANT: This page was generated from comments in the Flux source code. Any
edits made directly to this page will be overwritten the next time the
documentation is generated. 

To make updates to this documentation, update the function comments above the
function definition in the Flux source code:

https://github.com/influxdata/flux/blob/master/stdlib/strings/strings.flux#L430-L430

Contributing to Flux: https://github.com/influxdata/flux#contributing
Fluxdoc syntax: https://github.com/influxdata/flux/blob/master/docs/fluxdoc.md

------------------------------------------------------------------------------->

`strings.index()` returns the index of the first instance of a substring in a string.
If the substring is not present, it returns `-1`.



##### Function type signature

```js
(substr: string, v: string) => int
```

{{% caption %}}For more information, see [Function type signatures](/flux/v0.x/function-type-signatures/).{{% /caption %}}

## Parameters

### v
({{< req >}})
String value to search.



### substr
({{< req >}})
Substring to search for.




## Examples

### Find the index of the first occurrence of a substring

```js
import "sampledata"
import "strings"

sampledata.string()
    |> map(fn: (r) => ({r with _value: strings.index(v: r._value, substr: "g")}))

```

{{< expand-wrapper >}}
{{% expand "View example input and output" %}}

#### Input data

| _time                | *tag | _value      |
| -------------------- | ---- | ----------- |
| 2021-01-01T00:00:00Z | t1   | smpl_g9qczs |
| 2021-01-01T00:00:10Z | t1   | smpl_0mgv9n |
| 2021-01-01T00:00:20Z | t1   | smpl_phw664 |
| 2021-01-01T00:00:30Z | t1   | smpl_guvzy4 |
| 2021-01-01T00:00:40Z | t1   | smpl_5v3cce |
| 2021-01-01T00:00:50Z | t1   | smpl_s9fmgy |

| _time                | *tag | _value      |
| -------------------- | ---- | ----------- |
| 2021-01-01T00:00:00Z | t2   | smpl_b5eida |
| 2021-01-01T00:00:10Z | t2   | smpl_eu4oxp |
| 2021-01-01T00:00:20Z | t2   | smpl_5g7tz4 |
| 2021-01-01T00:00:30Z | t2   | smpl_sox1ut |
| 2021-01-01T00:00:40Z | t2   | smpl_wfm757 |
| 2021-01-01T00:00:50Z | t2   | smpl_dtn2bv |


#### Output data

| _time                | _value  | *tag |
| -------------------- | ------- | ---- |
| 2021-01-01T00:00:00Z | 5       | t1   |
| 2021-01-01T00:00:10Z | 7       | t1   |
| 2021-01-01T00:00:20Z | -1      | t1   |
| 2021-01-01T00:00:30Z | 5       | t1   |
| 2021-01-01T00:00:40Z | -1      | t1   |
| 2021-01-01T00:00:50Z | 9       | t1   |

| _time                | _value  | *tag |
| -------------------- | ------- | ---- |
| 2021-01-01T00:00:00Z | -1      | t2   |
| 2021-01-01T00:00:10Z | -1      | t2   |
| 2021-01-01T00:00:20Z | 6       | t2   |
| 2021-01-01T00:00:30Z | -1      | t2   |
| 2021-01-01T00:00:40Z | -1      | t2   |
| 2021-01-01T00:00:50Z | -1      | t2   |

{{% /expand %}}
{{< /expand-wrapper >}}
