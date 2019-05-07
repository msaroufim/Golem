# Alternatives

## RL control center
* https://github.com/awjuliani/RL-CC/blob/master/Double-Dueling-DQN-Central.ipynb
* Plots error and number of steps per episode in graphs
* Shows value of states and advantage of different action


Logger looks like and can be seen in the main script

```python
with open('./Center/log.csv', 'w') as myfile:
    wr = csv.writer(myfile, quoting=csv.QUOTE_ALL)
    wr.writerow(['Episode','Length','Reward','IMG','LOG'])  
```

Results visualized in HTML using D3
* Lots of nice helper functions
* Event triggers for mouse overs

```javascript
d3.csv("/data/cities.csv").then(function(data) {
  console.log(data[0]);
});
```

Most D3 visualizations have some sort of attribute that needs to be set and can set triggers

```javascript
    g2.append("rect")
      .attr("class", "overlay")
      .attr("id","overlayB")
      .attr("width", width)
      .attr("height", height)
      .on("mouseover", function() {canResetLine = false;})
      .on("mouseleave",function() {canResetLine = true;})
      .on("mousemove", mousemoveG2)
      .on("mousedown", setEpisode);
```

## Tensorboard
Nice 1 line description: TensorBoard is a webapp for understanding TensorFlow runs and graphs.


In your code

```python
file_writer = tf.summary.FileWriter('/path/to/logs', sess.graph)
```

From the command line

```
tensorboard --logdir path/to/logs
```

Tensorboard hsa tools to visualize time series over time and tensors over time

Experiment format

    [{
      "id": 123,
      "names": "train",
      "startTime": 1234567,
      "tags": [{
        "id": 789,
        "displayName": "",
        "name": "loss",
        "pluginName": "scalar"
      }]
    }]


* Has managing utilities to manage several experiments
* Special utilities to work with Ipython. Ipython has its own API to display stuff on screen. Ipython can render HTML so tensorboard sends the entire tensorflow frontend through it as HTML with some javascript in it
* Command line interface
* Tensorboard backend uses SQL lite
* Tensorboard uses a URL shortener with werkzeug
* LOL google fonts are blocked in china
* Takes in a graph representation and can output it
* Their tests involve generatin random data
* Tensorboard has a bunch of typescript scripts in a folder called components. Those files are compared to js and then referenced in some html files which store the data to render a visualization and the rendering logic depending on application
* Possible to compare two models side by side. Different kinds of viz may be meaningful to look at in competitions. Uses component library called Polymer https://github.com/Polymer/polymer


## Leaderboard python
* https://github.com/agoragames/leaderboard-python
* Can get specific ranks, ranks around a player and top X
* Can add conditional functions that need to evaluate to true before you make an addition to the leaderboard
* Whole project is really tied to redis
    * redis allows batching of events using the pipeline command
    * Commands like cardinality and counts are all O(1) (as you'd expect from a key value store)