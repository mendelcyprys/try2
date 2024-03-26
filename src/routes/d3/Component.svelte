<script lang="ts">
  import * as d3 from "d3";
  import { Slider } from "$lib/components/ui/slider";
  import Button from "$lib/components/ui/button/button.svelte";

  let rotation: [[number], [number], [number]];
  function initAngles() {
    rotation = [[5], [-25.3], [0]];
  }
  initAngles();

  $: projection = d3
    .geoOrthographic().clipAngle(180.000001)
    .rotate(rotation.flat() as [number, number, number])
    .translate([260, 260]);
  $: path = d3.geoPath(projection);
  $: graticule = d3.geoGraticule().step([20, 5]);
  const circle = d3.geoCircle();
</script>

<div class="flex flex-row gap-5 items-center">
  <svg width="520" height="520" xmlns="http://www.w3.org/2000/svg">
    <path
      d={path(graticule())}
      style="fill:none;stroke:rgba(0, 0, 0, 0.2);stroke-width:1"
    />
    <path
      d={path(circle.center([0, 90]).radius(90)())}
      style="fill:none;stroke:rgba(0, 0, 0, 0.5);stroke-width:2"
    />
    <path
      d={path(circle.center([130, 68]).radius(90)())}
      style="fill:none;stroke:rgba(0, 0, 0, 0.5);stroke-width:2"
    />
    <path
      d={path(circle.center([130, 68]).radius(50)())}
      style="fill:none;stroke:rgba(0, 0, 0, 0.5);stroke-width:2"
    />
    <path
      d={path({ type: "LineString", coordinates: [[40, 0], [-20, 19.25]] })}
      style="fill:none;stroke:rgba(100, 0, 0, 0.5);stroke-width:5"
    />
  </svg>
  <div class="flex flex-col gap-5 w-64">
    <Slider bind:value={rotation[0]} min={-120} max={120} step={0.5} />
    <Slider bind:value={rotation[1]} min={-120} max={120} step={0.5} />
    <Slider bind:value={rotation[2]} min={-120} max={120} step={0.5} />
    <Button variant="outline" on:click={initAngles}>Reset</Button>
  </div>
</div>
