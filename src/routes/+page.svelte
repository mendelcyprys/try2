<script lang="ts">
    import katex from 'katex';
</script>

<p>{@html katex.renderToString("\\int^{\\infty}_{-\\infty} \\exp\\left(-x^2\\right) \\cdot \\sin(x) \\ \\text{d}x", { displayMode: true })}</p>
