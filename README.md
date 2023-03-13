# svelte-heatmap

A light weight and customizable version of GitHub's contribution graph.

[![Heatmap examples](https://user-images.githubusercontent.com/7980426/78958159-27d55280-7a9c-11ea-9b08-8b5d7df31d7a.png)](https://svelte-heatmap.netlify.app/)

## 📦 Installation

- clone `https://github.com/FelipeIzolan/svelte-heatmap.git`
- add svelte-heatmap folder in your project folder.
- `import SvelteHeatmap from "path/to/svelte-heatmap";`


## 🚀 Basic usage

To create a heatmap, pass `props` to the `SvelteHeatmap` constructor.

```svelte
<script>
import SvelteHeatmap from './svelte-heatmap';

const start = new Date(); // year begin
start.setMonth(0, 1);
start.setHours(0, 0, 0, 0);

const end = new Date(); // year end
end.setMonth(11, 30);

const data = new Map();
data.set("2023-01-25", 1);
data.set("2023-01-24", 8);
data.set("2023-01-23", 3);
data.set("2023-01-22", 5);
data.set("2023-07-01", 10);
data.set("2023-05-11", 4);
</script>

<SvelteHeatmap
  data={data}
  colors={['#404040', '#303030', '#202020', '#101010']}
  dayLabels={['Sun', 'Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat']}
  dayLabelWidth={10}
  monthLabelHeight={6}
  startDate={start}
  endDate={end}
  view={'yearly'}
  fontSize={4}
  cellSize={4}
  cellGap={1}
/>
```

## ⚙️ Options

> **Note:** Date values for `data`, `startDate`, and `endDate` should be [JavaScript `Date` objects](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date) objects, or a value compatible with the Date constructor.

##### `allowOverflow`

Renders cells that fall outside the `startDate` to `endDate` range. Defaults to `false`.

##### `cellGap`

Defines the space between cells.

##### `cellRadius`

Defines the radius of each cell. This should be a number relative to the `cellSize`, or a string representing a percentage such as `'50%'`.

##### `cellSize`

Defines the size of each cell.

##### `cellClick`

Defines a function to be executed on click.

##### `colors`

Array of CSS colors to use for the chart, ordered from lowest to highest. Default colors match GitHub's contribution graph with `['#c6e48b', '#7bc96f', '#239a3b', '#196127']`.

##### `data`

Map object.

key - YYYY-MM-DD (ISO standard)\
value - number

##### `dayLabelWidth`

Horizontal space to allocate for day labels. If this is `0`, day labels will not be rendered.

##### `dayLabels`

Array of strings to use for day labels. Defaults to `['', 'Mon', '', 'Web', '', 'Fri', '']`.

##### `fontColor`

Label font color. Defaults to `#333`.

##### `fontFamily`

Label font family. Defaults to `sans-serif`.

##### `fontSize`

Label font size. Defaults to `8`.

##### `emptyColor`

CSS color to use for cells with no value.

##### `monthGap`

Defines the space between months when `view` is set to `monthly`.

##### `monthLabelHeight`

Vertical space to allocate for month labels. If this is `0`, month labels will not be rendered.

##### `monthLabels`

Array of strings to use for month labels. Defaults to `['Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun', 'Jul', 'Aug', 'Sep', 'Oct', 'Nov', 'Dec']`.

##### `startDate`

Date object representing the first day of the graph. If omitted, this will default to the first day of the `month` or `year`, based on the current `view`.

##### `endDate`

Date object represending the last day of the graph. If omitted, this will default to the last day of the current `month` or `year`, depending on the current `view`.

##### `view`

Determines how the chart should be displayed. Supported values are `monthly` and `yearly`, defaults to `yearly`.

## 📄 License

[MIT](https://github.com/scottbedard/svelte-heatmap/blob/master/LICENSE)

Copyright (c) 2017-present, Scott Bedard
