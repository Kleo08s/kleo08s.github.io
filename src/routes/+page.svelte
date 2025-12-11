<script lang="ts">
  import { Sun, ExternalLink, Rss, Gamepad2, Music } from '@lucide/svelte';
  
  import { Progress } from "$lib/components/ui/progress/index.js";

  import * as Tooltip from "$lib/components/ui/tooltip/index.js";
  
  import { onMount } from 'svelte';

  // const resizeAllGridItems = () => {
  //   const grid = document.querySelector('.grid-main') as HTMLElement | null;
  //   if (!grid) return;

  //   const rowHeight = 1;
  //   const rowGap = parseFloat(getComputedStyle(grid).rowGap);

  //   grid.querySelectorAll<HTMLElement>('.element').forEach((item) => {
  //     item.style.gridRowEnd = 'auto';
  //     const height = item.offsetHeight;
  //     const rowSpan = Math.ceil((height + rowGap) / (rowHeight + rowGap));
  //     item.style.gridRowEnd = `span ${rowSpan}`;
  //   });
  // };

  // onMount(() => {
  //   setTimeout(resizeAllGridItems, 0);
  //   window.addEventListener('resize', resizeAllGridItems);

  //   return () => window.removeEventListener('resize', resizeAllGridItems);
  // });
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

  <div class="element">
    <h1>22:35:38</h1>
    <p>Europe/Rome</p>
  </div>
  
  <div class="element">
    <div class="inlineicon" style="margin-bottom: -1rem;">
      <h2><Rss />Status</h2>
    </div>

    <div id="status-empty" style="margin-top: 1rem">
      <i>Currently doing nothing...</i>
    </div>

    <div id="status-gaming" style="display: inline-flex; align-items: center">
      <div style="position: relative; display: inline-block">
        <Tooltip.Root>
          <Tooltip.Trigger><img src="https://raw.githubusercontent.com/LeonardSSH/vscord/main/assets/icons/css.png" alt="Kleo08s's current PFP" id="image-large"></Tooltip.Trigger>
          <Tooltip.Content><p>Editing a .CSS file</p></Tooltip.Content>
        </Tooltip.Root>
        <Tooltip.Root>
          <Tooltip.Trigger><img src="https://raw.githubusercontent.com/LeonardSSH/vscord/main/assets/icons/vscode.png" alt="" id="image-small" style="position: absolute; bottom: 0; right: 0; border-radius: 50%; width: 2.75rem; height: 2.75rem; margin: -0.5rem; border: 0.25rem solid var(--card);"></Tooltip.Trigger>
          <Tooltip.Content><p>Visual Studio Code</p></Tooltip.Content>
        </Tooltip.Root>
      </div>
      <div style="display: flex; flex-direction: column; margin-left: 1rem">
        <h2>Code</h2>
        <p>In kleo08s.github.io - 4 problems found</p>
        <p>Working on app.css:206:2</p>
        <p style="display: flex; gap: 0.5rem; color: #2ecc71; font-weight: bold; font-family: var(--font-mono); margin-top: 0.25rem"><Gamepad2 />19:38</p>
      </div>
    </div>

    <div id="status-music" style="display: inline-flex; align-items: center; width: inherit">
      <Tooltip.Root>
        <Tooltip.Trigger><img src="https://i.scdn.co/image/ab67616d0000b273f9cfbf4187cef596c5f8df9c" alt="Kleo08s's current PFP" id="image-large"></Tooltip.Trigger>
        <Tooltip.Content><p>Tera I / O</p></Tooltip.Content>
      </Tooltip.Root>
      <div style="display: flex; flex-direction: column; margin-left: 1rem; width: inherit; overflow-wrap: break-word;">
        <h2 style="overflow-wrap: anywhere;">Flamewall</h2>
        <p style="overflow-wrap: anywhere;">Camellia</p>
        <div style="display: flex; gap: 1rem; margin-top: 0.5rem">
          <p style="font-family: var(--font-mono); color: #2ecc71; font-weight: bold; overflow-wrap: normal;">1:21</p>
          <Progress color="#2ecc71" value={33} style="margin-top: 0.5rem" />
          <p style="font-family: var(--font-mono); color: #2ecc71; font-weight: bold; overflow-wrap: normal;">4:32</p>
        </div>
      </div>
    </div>
  </div>

  <div class="element">
    <div class="inlineicon">
      <h2><Music />Music<ExternalLink size="20" style="margin-left: auto" /></h2>
    </div>
    <div style="display: flex; align-items: baseline; gap: 0.5rem;">
      <h1>16.321</h1>
      <p>scrobbles</p>
      <p style="filter: opacity(0.25);">since 29 june 2024</p>
    </div>

    <h2>Last 3 songs</h2>
    <div class="music-top-main">
      <div class="music-top-element">
        <img src="https://i.scdn.co/image/ab67616d0000b273f9cfbf4187cef596c5f8df9c" alt="Kleo08s's current PFP" id="image-large">
        <h3>Fra Martino campanaro</h3>
        <p>Coro Fonola band</p>
      </div>
      <div class="music-top-element">
        <img src="https://i.scdn.co/image/ab67616d0000b273f9cfbf4187cef596c5f8df9c" alt="Kleo08s's current PFP" id="image-large">
        <h3>Mmhmm</h3>
        <p>BigXthaPlug</p>
      </div>
      <div class="music-top-element">
        <img src="https://i.scdn.co/image/ab67616d0000b273f9cfbf4187cef596c5f8df9c" alt="Kleo08s's current PFP" id="image-large">
        <h3>Napoli Tirana</h3>
        <p>Stresi</p>
      </div>
    </div>
  </div>
</div>
<div class="shadow-bottom"></div>