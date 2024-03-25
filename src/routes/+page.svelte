<script lang="ts">
  import katex from "katex";
</script>

<div class="text-3xl">
  {@html katex.renderToString(
    String.raw`\int^{\infty}_{-\infty} \exp \left( -x^2 \right) \cdot \sin(x) \ \text{d}x`,
    { displayMode: true }
  )}
</div>
<h1>tailwind test</h1>
