---
layout: page
name: Testing
custom-javascript-list:
  - "https://d3js.org/d3.v4.js"
  - "https://d3js.org/d3-scale-chromatic.v1.min.js"
  - "https://d3js.org/d3-geo-projection.v2.min.js"
---

<svg id="my_dataviz" width="800" height="600"></svg>

<script>

var svg = d3.select("svg"),
  width = +svg.attr("width"),
  height = +svg.attr("height");

var path = d3.geoPath();
var projection = d3.geoMercator()
  .scale(70)
  .center([0,20])
  .translate([width / 2, height / 2]);

var data = d3.map();
var colorScale = d3.scaleThreshold()
  .domain([100000, 1000000, 10000000, 30000000, 100000000, 500000000])
  .range(d3.schemeBlues[7]);

d3.queue()
  .defer(d3.json, "https://raw.githubusercontent.com/holtzy/D3-graph-gallery/master/DATA/world.geojson")
  .defer(d3.csv, "https://raw.githubusercontent.com/holtzy/D3-graph-gallery/master/DATA/world_population.csv", function(d) { data.set(d.code, +d.pop); })
  .await(ready);

function ready(error, topo) {

  svg.append("g")
    .selectAll("path")
    .data(topo.features)
    .enter()
    .append("path")
      // draw each country
      .attr("d", d3.geoPath()
        .projection(projection)
      )
      .attr("fill", function (d) {
        d.total = data.get(d.id) || 0;
        return colorScale(d.total);
      });
    }

</script>
