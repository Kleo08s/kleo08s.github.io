<script lang="ts">
    import * as icon from '@lucide/svelte';

    import { Button } from "$lib/components/ui/button/index.js";
</script>

<style>
    .navbar-main {
        width: 67rem;
        background: var(--navbar-background);
        border-radius: var(--radius-xl);
        height: 3.5rem;
        position: fixed;
        margin-top: 2rem;
        margin-left: auto;
        margin-right: auto;
        left: 0;
        right: 0;
        display: flex;
        align-items: center;
        justify-content: space-between;
    }

    .navbar-main .start, .navbar-main .end {
        margin-left: 1rem;
        margin-right: 0.75rem;
        display: flex;
        align-items: center;
        gap: 1rem;
    }
</style>
<div class="navbar-main">
    <div class="start">
        <h2>Kleo08s</h2>
    </div>
    <div class="end">
        <icon.Grip />
        <Button>Discord Server</Button>
    </div>
</div>
