<script lang="ts">
  import * as d3 from "d3";
  import { Slider } from "$lib/components/ui/slider";
  import Button from "$lib/components/ui/button/button.svelte";

  let rotation: [[number], [number], [number]];
  function initAngles() {
    rotation = [[0], [-25.3], [0]];
  }
  initAngles();

  $: projection = d3
    .geoOrthographic()
    .rotate(rotation.flat() as [number, number, number])
    .translate([260, 260]);
  $: path = d3.geoPath(projection);
  const circle = d3.geoCircle();
</script>

<div class="flex flex-row gap-5 items-center">
  <svg width="520" height="520" xmlns="http://www.w3.org/2000/svg">
    <path
      d={path({ type: "Sphere" })}
      style="fill:none;stroke:rgba(0, 0, 0, 1);stroke-width:2"
    />
    <path
      d={path(d3.geoGraticule10())}
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
  </svg>
  <div class="flex flex-col gap-5 w-64">
    <Slider bind:value={rotation[0]} min={-120} max={120} step={0.5} />
    <Slider bind:value={rotation[1]} min={-120} max={120} step={0.5} />
    <Slider bind:value={rotation[2]} min={-120} max={120} step={0.5} />
    <Button variant="outline" on:click={initAngles}>Reset</Button>
  </div>
</div>
