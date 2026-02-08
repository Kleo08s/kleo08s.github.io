<script lang="ts">
  import { fade } from 'svelte/transition';
  import { tweened } from 'svelte/motion';
  import { cubicOut } from 'svelte/easing';

  import * as config from '$lib/config';
  import Navbar from "$lib/components/navbar.svelte";

  const blur = tweened(15, { duration: 150, easing: cubicOut });
  const alpha = tweened(0.75, { duration: 250, easing: cubicOut });

  let showWelcome = true;

  function enableAudio() {
    const audio = document.getElementById('bg-audio') as HTMLAudioElement;
    const video = document.getElementById('bg-video') as HTMLVideoElement;

    audio.volume = 0.2;
    audio.play();
    video.play();

    blur.set(0);
    alpha.set(0);
    showWelcome = false;
  }
</script>

<style>
  .welcome {
    background-color: var(--welcome-background);
    backdrop-filter: blur(10px);
    border-radius: 0;
    width: 100%;
    height: 100%;
    position: fixed;
    text-align: center;
    align-content: center;
    z-index: 999;
    font-size: xx-large;
    font-weight: bold;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .welcome button {
    width: 100%;
    height: 100%;
    cursor: pointer;
  }

  .bg-video {
    position: fixed;
    top: 0;
    left: 0;
    width: 100vw;
    height: 100vh;
    object-fit: cover;
    z-index: -1;
    opacity: 0.5;
  }

  .main {
    padding-top: 10rem;
    display: flex;
    justify-content: space-between;
    margin-left: auto;
    margin-right: auto;
    width: max-content;
    gap: 2.5rem;
  }

  .main .element {
    padding: 1.5rem;
    background-color: var(--card);
    width: 25rem;
    border-radius: var(--radius-xl);
    border: 1px solid var(--border);
    margin-bottom: 2.5rem;
    backdrop-filter: blur(10px);
  }

  .profile #banner {
    width: 100%;
    height: 7.5rem;
    object-fit: cover;
    border: 1px solid var(--border);
    border-radius: var(--radius-xl) var(--radius-xl) 0 0;
  }

  .profile #pfp {
    width: 6rem;
    height: 6rem;
    margin-left: 2rem;
    margin-top: -3.5rem;
    position: relative;
    border-radius: 100%;
    border: 1px solid var(--border);
  }

  .profile h2 {
    margin-left: 1.5rem;
    margin-top: 0.5rem;
  }

  .profile p {
    text-align: center;
    color: var(--muted-foreground);
  }

  .profile .name {
    display: flex;
    align-items: center;
    gap: 1rem;
  }

  .profile .name .badge {
    background-color: var(--secondary);
    padding: 0.25rem;
    padding-left: 0.75rem;
    padding-right: 0.75rem;
    margin-top: 0.5rem;
    display: flex;
    gap: 0.5rem;
    width: max-content;
    height: 1.75rem;
    align-items: center;
    border-radius: var(--radius-lg);
    border: 1px solid var(--border);
  }

  .profile .name .badge b {
    font-size: 13px;
  }

  .profile .name .badge img {
    height: 1rem;
  }

  .profile .bio {
    background-color: var(--secondary);
    border-radius: var(--radius-lg);
    margin: 1rem;
    padding: 1rem;
    border: 1px solid var(--border);
  }

  .profile .bio h4 {
    margin-top: -0.25rem;
    font-weight: bold;
    color: var(--muted-foreground);
  }

  .profile .bio p {
    color: var(--foreground);
    text-align: start;
    margin-top: 0.25rem;
  }
</style>

<Navbar />

<video loop muted playsinline class="bg-video" id="bg-video">
  <source src="https://r2.guns.lol/0abd16f5-8565-46a8-b8de-2865d5ec4c09.mp4" type="video/mp4">
</video>

<audio id="bg-audio" loop>
  <source src="https://r2.guns.lol/a8d2e150-8a24-49e1-8087-30059afabf30.mp3" type="audio/mpeg">
</audio>

<div class="welcome" style="backdrop-filter: blur({$blur}px); background-color: oklch(0.141 0.005 285.823 / {$alpha});">
  {#if showWelcome}
    <button on:click={enableAudio} style="margin-top: 2rem; font-family: var(--font-header); color: white" transition:fade>Inferno...</button>
  {/if}
</div>

<div class="main">
  <div class="grid1">
    <div class="profile element" style="padding-top: 0; padding-left: 0; padding-right: 0">
      <img id="banner" src={config.profile.banner} alt="Banner">
      <img id="pfp" src={config.profile.pfp} alt="PFP">
      <div class="name">
        <h2>{config.profile.name}</h2>
        <div class="badge">
          <img src="https://cdn.discordapp.com/clan-badges/398627612299362304/9c28f5002410f1d1679d0e6a99609ef4.png?size=64" alt="GD Badge">
          <b>GD</b>
        </div>
      </div>
      <div class="bio">
        <h4>ABOUT ME</h4>
        <p>{config.profile.bio}</p>
      </div>
    </div>
    <div class="element">
      <h2>Profile</h2>
    </div>
  </div>
  <div class="grid2">
    <div class="element">
      <h2>Activity</h2>
    </div>
  </div>
  <div class="grid3">
    <div class="element">
      <h2>Bg music</h2>
    </div>
    <div class="element">
      <h2>Lastfm stats</h2>
    </div>
  </div>
</div>
