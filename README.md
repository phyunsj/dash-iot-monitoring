# IoT Dashboard Design with Dash

>:pushpin: **The intention of this excericse is to undersatand communications between the front-end generated by Dash framewotk and the back-end. The heavy lifting is done by Dash framework. Any web application serving GET/POST methods can utilize Dash front-end implementaion.**

"Dash is a Python framework for building analytical web applications. No JavaScript required. Build on top of Plotly.js, React, and Flask, Dash ties modern UI elements like dropdowns, sliders, and graphs directly to your analytical python code." ..._from [Dash by plotly](https://plot.ly/products/dash/)_

**Additional Info on _Dash_**
 - [Introducing Dash](https://medium.com/@plotlygraphs/introducing-dash-5ecf7191b503)
 - [Dash App Gallery](https://dash.plot.ly/gallery)

## Example 1. Chart Display 

 Started with the first example from [Dash User Guide](https://dash.plot.ly/getting-started), set  interval=3000 (3 secs) and defined [callbacks](https://dash.plot.ly/getting-started-part-2). 

<p align="center">
<img src="https://github.com/phyunsj/iot-dashboard-design-with-dash/blob/master/images/dash-example1.png" width="600px"/>
</p>

 `index.html`, `_dash-layout`, `_dash-dependencies` are generated by Dash framework. Use it directly on Node-RED `template` node. For [live-update](https://dash.plot.ly/live-updates), the back-end responds `_dash-update-component` request every 3 secs (interval=3000). 

<p align="center">
<img src="https://github.com/phyunsj/iot-dashboard-design-with-dash/blob/master/images/node-red-example1.gif" width="600px"/>
</p>


## Example 2. Wind Speed Monitoring

The original work is done in [here(Dash Wind Streaming App)](https://github.com/plotly/dash-wind-streaming). The sample data `wind-data.db` is also provided. 

**UPDATE** [Dash Wind Streaming App](https://github.com/plotly/dash-sample-apps/tree/master/apps/dash-wind-streaming) : new location & new look.

<p align="center">
<img src="https://github.com/phyunsj/iot-dashboard-design-with-dash/blob/master/images/dash-example2.png" width="650px"/>
</p>

Install `node-red-node-sqlite` to access `wind-data.db`. Manually create **_DATA_** for `{ response: {props: {figure: { data : [DATA], layout : ...}`.  Node-RED (or any web application) serves two types of POST requests (`wind-speed` and `wind-direction`) for this example. The original work has one additional POST request (`wind-histogram`).

[plotly.js-dist](https://www.npmjs.com/package/plotly.js-dist) can be used instead in `function` node. See [how to use `require` in Node-RED `function` node.](https://github.com/phyunsj/node-red-simple-blocking-queue)

<p align="center">
<img src="https://github.com/phyunsj/iot-dashboard-design-with-dash/blob/master/images/node-red-example2-windspeed.gif" width="650px"/>
</p>
 

## Other Consideration

[shinydashboard](https://rstudio.github.io/shinydashboard/index.html) makes it easy to use Shiny to create dashboards
