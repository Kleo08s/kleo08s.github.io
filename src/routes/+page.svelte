<script lang="ts">
  import { onMount } from 'svelte';

  const resizeAllGridItems = () => {
    const grid = document.querySelector('.grid-main') as HTMLElement | null;
    if (!grid) return;

    const rowHeight = 1; // deve corrispondere a grid-auto-rows
    const rowGap = parseFloat(getComputedStyle(grid).rowGap);

    grid.querySelectorAll<HTMLElement>('.element').forEach((item) => {
      item.style.gridRowEnd = 'auto'; // reset temporaneo
      const height = item.offsetHeight;
      const rowSpan = Math.ceil((height + rowGap) / (rowHeight + rowGap));
      item.style.gridRowEnd = `span ${rowSpan}`;
    });
  };

  onMount(() => {
    // aspetta che il DOM sia renderizzato
    setTimeout(resizeAllGridItems, 0);
    window.addEventListener('resize', resizeAllGridItems);

    return () => window.removeEventListener('resize', resizeAllGridItems);
  });
</script>


<h1>Home</h1>
<div class="grid-main">
  <div class="element">
    <h2>Hello! My name is Kleo08s.</h2>
  </div>
  <div class="element">
    <h2>Hello! My name is Kleo08s.</h2>
    <h2>Hello! My name is Kleo08s.</h2>
    <h2>Hello! My name is Kleo08s.</h2>
  </div>
  <div class="element">
    <h2>Hello! My name is Kleo08s.</h2>
    <h2>Hello! My name is Kleo08s.</h2>
  </div>
  <div class="element">
    <h2>Hello! My name is Kleo08s.</h2>
  </div>
</div>
