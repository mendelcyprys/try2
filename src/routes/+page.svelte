<script lang="ts">
  import katex from "katex";
</script>

<div class="text-3xl">
  {@html katex.renderToString(
    String.raw`\int^{\infty}_{-\infty} \exp \left( -x^2 \right) \cdot \sin(x) \ \text{d}x`,
    { displayMode: true, fleqn: true }
  )}
</div>

<div class="hebrew m-10 text-4xl">
  המסלול הפתלתל שעברה השפה העברית והתהליכים הרבים שחלו בה במרוצת הדורות מכוננים
  עולם מחקרי מרתק, במהלך ההיסטוריה בא העם היהודי במגע עם תרבויות רבות מן העולם
  העתיק ומן העולם המודרני. מחקר ולימוד הלשון העברית חושפים בפני הלומדים את
  התמורות שחלו בשפה בעקבות מפגשים אלו.
</div>

<div class="hebrew2 m-10 text-4xl">
  המסלול הפתלתל שעברה השפה העברית והתהליכים הרבים שחלו בה במרוצת הדורות מכוננים
  עולם מחקרי מרתק, במהלך ההיסטוריה בא העם היהודי במגע עם תרבויות רבות מן העולם
  העתיק ומן העולם המודרני. מחקר ולימוד הלשון העברית חושפים בפני הלומדים את
  התמורות שחלו בשפה בעקבות מפגשים אלו.
</div>

<div class="hebrew3 m-10 text-4xl">
  המסלול הפתלתל שעברה השפה העברית והתהליכים הרבים שחלו בה במרוצת הדורות מכוננים
  עולם מחקרי מרתק, במהלך ההיסטוריה בא העם היהודי במגע עם תרבויות רבות מן העולם
  העתיק ומן העולם המודרני. מחקר ולימוד הלשון העברית חושפים בפני הלומדים את
  התמורות שחלו בשפה בעקבות מפגשים אלו.
</div>

<style>
  .hebrew {
    font-family: "Noto Serif Hebrew";
    font-variation-settings: "wght" 700, "wdth" 100;
    direction: rtl;
  }
  .hebrew2 {
    font-family: "SBL Hebrew";
    direction: rtl;
  }
  .hebrew3 {
    font-family: "Ezra SIL";
    direction: rtl;
    line-height: 60px;
    font-weight: 500;
  }
</style>
