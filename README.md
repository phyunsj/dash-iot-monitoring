# IoT Dashboard Design with Dash

Sample example to use Dash python framework for IoT Dashboard Design

"Dash is a Python framework for building analytical web applications. No JavaScript required. Build on top of Plotly.js, React, and Flask, Dash ties modern UI elements like dropdowns, sliders, and graphs directly to your analytical python code." ..._from [Dash by plotly](https://plot.ly/products/dash/)_

See more on [Dash Gallery](https://dash.plot.ly/gallery)


### GET `_dash-layout`

```
{"type" : "Div", "namespace":"dash_html_components", 
       { "props" :
           { "children" : [ ... ] }
       }
}
```

- [Dash Layout](https://dash.plot.ly/getting-started)


### GET `_dash-dependencies`

```
[{"events":[],"inputs":[{"id":"...","property":"value"}],"output":{"id":"...","property":"figure"},"state":[]}]

```


- [Dash Callbacks](https://dash.plot.ly/getting-started-part-2)


### POST `_dash-update-component`

POST Request
```
{ "output" : {} , "inputs" : [] }
```

POST Response
```
{ "response" : { "props" : { "figure" :
     { data : [...]   },
     { layout : {...} }
}  }  }
```


### Other Consideration

[shinydashboard for R](https://rstudio.github.io/shinydashboard/index.html)
