<script lang="ts">
  import katex from "katex";
  import * as d3 from "d3";

  import { text as newMoonText } from "$lib/texts/new-moon.json";
  import { text as foundationsTorah } from "$lib/texts/foundations-torah.json";
  import { onMount } from "svelte";

  onMount(() => {
    d3.select("#d3").append("p").text("Hello world");
  });
</script>

<div class="text-3xl">
  {@html katex.renderToString(
    String.raw`\int^{\infty}_{-\infty} \exp \left( -x^2 \right) \cdot \sin(x) \ \text{d}x`,
    { displayMode: true, fleqn: true }
  )}
</div>

<div class="hebrew m-10 text-4xl">
  {@html newMoonText[0][0]}
</div>

<div class="sbl m-10 text-4xl">
  {@html foundationsTorah[0][5]}
</div>

<div class="ezra m-10 text-4xl">
  {@html newMoonText[0][0]}
</div>

<div id="d3"></div>

<style>
  .hebrew {
    font-family: "Noto Serif Hebrew";
    font-variation-settings:
      "wght" 700,
      "wdth" 100;
    direction: rtl;
    line-height: 60px;
  }
  .sbl {
    font-family: "SBL Hebrew";
    direction: rtl;
    line-height: 60px;
  }
  .ezra {
    font-family: "Ezra SIL";
    direction: rtl;
    line-height: 60px;
  }
</style>
