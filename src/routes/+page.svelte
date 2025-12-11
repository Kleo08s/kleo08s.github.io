<script lang="ts">
  import { Sun, ExternalLink } from '@lucide/svelte';
  
  import { Progress } from "$lib/components/ui/progress/index.js";
  
  import { onMount } from 'svelte';

  const resizeAllGridItems = () => {
    const grid = document.querySelector('.grid-main') as HTMLElement | null;
    if (!grid) return;

    const rowHeight = 1;
    const rowGap = parseFloat(getComputedStyle(grid).rowGap);

    grid.querySelectorAll<HTMLElement>('.element').forEach((item) => {
      item.style.gridRowEnd = 'auto';
      const height = item.offsetHeight;
      const rowSpan = Math.ceil((height + rowGap) / (rowHeight + rowGap));
      item.style.gridRowEnd = `span ${rowSpan}`;
    });
  };

  onMount(() => {
    setTimeout(resizeAllGridItems, 0);
    window.addEventListener('resize', resizeAllGridItems);

    return () => window.removeEventListener('resize', resizeAllGridItems);
  });
</script>

<div class="shadow-up"></div>
<h1 style="position: fixed; z-index: 999; margin-left: 1rem; margin-top: -1rem">Home</h1>
<div class="grid-main">
  <div class="element">
    <div style="display: flex; margin-bottom: 1rem; align-items: center">
      <img src="https://cdn.discordapp.com/avatars/407804601551683584/93974bbe918462434787b4eb2c959d14?size=1024" alt="Kleo08s's current PFP">
      <h2 style="margin-left: 1rem;">Hello! My name is Kleo08s.</h2>
    </div>
    <p>I'm a silly <b>17 years old</b> 🇮🇹 Italian 👨‍💻 developer and 🎮 gamer</p>
    <div style="display: flex; justify-content: space-between; margin-top: 1rem">
      <p><i>My life span</i></p>
      <p><b>22,979%</b></p>
    </div>
    <Progress value={6518} max={28365} style="margin-top: 0.5rem" />
  </div>
  <div class="element">
    <div class="inlineicon">
      <h2><Sun />Weather<ExternalLink size="20" style="margin-left: auto" /></h2>
    </div>
    <div class="inlineicon">
      <h2 style="font-size: 2.25rem; margin-left: 1.5rem; display: flex; align-items: center; gap: 1rem">
        <Sun size="50" style="flex-shrink: 0" />
        <div style="display: flex; flex-direction: column">
          <span>Sunny</span>
          <span style="font-family: var(--font-body); font-size: 1.25rem">27°C (min 21°C max 29°C)</span>
        </div>
      </h2>
    </div>
  </div>
</div>
<div class="shadow-bottom"></div>