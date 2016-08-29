# chart_js_level_areas_plugin
A plugin for drawing level areas on Chart.js 2.0+.

### Installation

Require this file after you have required Chart.js.

### Test
You can open test.html to see the plugin in action.

### Usage

Pass an additional levelAreas array to the options key.
Each levelAreas entry must have 'from' and 'to' values, which are y-values.
Optionally they can have style and text.
Style should be a semi-transparent color.

```javascript
// Example

var data = {
    labels: ["JAN", "FEB", "MAR", "APR", "MAY", "JUN", "JUL", "AUG", "SEP", "OCT", "NOV", "DEC"],
    datasets: [{
        data: [1.5, 3, 2, 1, 8, 8, 2, 2, 3, 5, 12, 1],
        fill: false,
        borderColor: "gray"
    }]
};

var ctx = document.getElementById("myChart").getContext("2d");

new Chart(ctx, {
		type: 'line',
    data: data,
    options: {
      responsive: false,
      maintainAspectRatio: false,
      levelAreas: [{
        from: 6,
        to: 10,
        style: "rgba(150,150,0,0.5)",
        text: "Warning"
      },{
        from: 10,
        to: 12,
        style: "rgba(215,100,100,0.5)",
        text: "Danger"
      }]
    }

});
```
