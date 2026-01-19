<script lang="ts">
  import * as icon from '@lucide/svelte';
  
  import Navbar from "$lib/components/navbar.svelte";

  import * as config from '$lib/config'
</script>

<style>
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
  }

  #banner-wrap {
    height: 7.5rem;
    border-radius: var(--radius-xl);
    overflow: hidden;
    position: relative;
  }

  #banner-wrap::after {
    content: "";
    position: absolute;
    inset: 0;
    box-shadow: inset 0 -8px 12px var(--card);
    pointer-events: none;
  }

  #banner {
    width: 100%;
    height: 100%;
    object-fit: cover;
    filter: opacity(0.5);
  }

  #profile #pfp {
    width: 6.5rem;
    height: 6.5rem;
    margin-left: auto;
    margin-right: auto;
    margin-top: -3rem;
    position: relative;
    border-radius: 100%;
    border: 1px solid var(--border);
  }

  #profile h2 {
    text-align: center;
    margin-top: 1rem;
  }

  #profile p {
    text-align: center;
    color: var(--muted-foreground);
  }
</style>

<Navbar />

<div class="main">
  <div class="grid1">
    <div id="profile" class="element" style="padding-top: 0; padding-left: 0; padding-right: 0">
      <div id="banner-wrap">
        <img id="banner" src={config.profile.banner} alt="Banner">
      </div>
      <img id="pfp" src={config.profile.pfp} alt="PFP">
      <h2>{config.profile.name}</h2>
      <p>{config.profile.bio}</p>
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