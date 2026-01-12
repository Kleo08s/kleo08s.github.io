<script lang="ts">
    import * as icon from '@lucide/svelte';

    import { Button } from "$lib/components/ui/button/index.js";
    import { buttonVariants } from "$lib/components/ui/button/index.js";
    import { Input } from "$lib/components/ui/input/index.js";
    import { Label } from "$lib/components/ui/label/index.js";

    import * as Popover from "$lib/components/ui/popover/index.js";
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

    .app-list {
        display: grid;
        grid-template-columns: 1fr 1fr;
        gap: 1rem;
        margin-top: 1rem;
    }

    .app-list .element {
        background: var(--secondary);
        padding-top: 0.5rem;
        padding-bottom: 0.5rem;
        padding-left: 1rem;
        padding-right: 1rem;
        border-radius: var(--radius-xl);
        display: flex;
        gap: 1rem;
        align-items: center;
        justify-content: space-evenly;
        border: 1px solid var(--border);
    }

    .app-list .element img {
        width: 2.5rem;
        height: 2.5rem;
    }

    .app-list .element p {
        font-size: 12px;
        color: var(--muted-foreground);
    }
</style>
<div class="navbar-main">
    <div class="start">
        <h2>Kleo08s</h2>
    </div>
    <div class="end">
        <Popover.Root open={true}>
            <Popover.Trigger><icon.Grip style="cursor: pointer" /></Popover.Trigger>
            <Popover.Content class="w-130 rounded-[15px]" >
                <h3>Apps</h3>
                <p>To get access to my self-hosted app email me. It's not guaranteed 100% i will make an account for you, i accept only my friends.</p>
                <div class="app-list" style="grid-template-columns: 1fr;">
                    <div class="element">
                        <img src="https://auth.kleo08s.lol/favicon.ico" alt="Logo">
                        <div style="width: 100%;">
                            <b>Authelia</b>
                            <p>The main OAuth Provider</p>
                        </div>
                        <a href="https://auth.kleo08s.lol/"><icon.ExternalLink size=20 /></a>
                    </div>
                </div>
                <div class="app-list">
                    <div class="element">
                        <img src="https://file.kleo08s.lol/api/favicon" alt="Logo">
                        <div style="width: 100%;">
                            <b>Erugo</b>
                            <p>File sharing</p>
                        </div>
                        <a href="https://file.kleo08s.lol/"><icon.ExternalLink size=20 /></a>
                    </div>
                    <div class="element">
                        <img src="https://git.kleo08s.lol/assets/img/favicon.png" alt="Logo">
                        <div style="width: 100%;">
                            <b>Gitea</b>
                            <p>Repo hosting</p>
                        </div>
                        <a href="https://git.kleo08s.lol/"><icon.ExternalLink size=20 /></a>
                    </div>
                </div>
            </Popover.Content>
        </Popover.Root>
        <Button>Discord Server</Button>
    </div>
</div>
