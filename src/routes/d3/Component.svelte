<script lang="ts">
  import * as d3 from "d3";

  const projection = d3.geoOrthographic().rotate([100, -30, 0]).translate([250, 250]);
  const path = d3.geoPath(projection);
</script>

<svg width="500" height="500" xmlns="http://www.w3.org/2000/svg">
  <path
    d={path({ type: "Sphere" })}
    style="fill:none;stroke:rgba(0, 0, 0, 0.5);stroke-width:1"
  />
  <path
    d={path(d3.geoGraticule10())}
    style="fill:none;stroke:rgba(0, 0, 0, 0.2);stroke-width:1"
  />
  <path
    d={path({ type: "LineString", coordinates: [[-90, 0], [0, 40], [90, 0], [180, -40], [-90, 0]]})}
    style="fill:none;stroke:rgba(0, 0, 0, 1);stroke-width:1"
  />
</svg>
