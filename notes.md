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