<script lang="ts">
    import * as icon from '@lucide/svelte';

    import { Button } from "$lib/components/ui/button/index.js";
    import { badgeVariants } from "$lib/components/ui/badge/index.js";

    import * as Popover from "$lib/components/ui/popover/index.js";
    import * as NavigationMenu from "$lib/components/ui/navigation-menu/index.js";
    import * as DropdownMenu from "$lib/components/ui/dropdown-menu/index.js";
</script>

<style>
    .navbar-main {
        width: 67rem;
        background: var(--navbar-background);
        border-radius: var(--radius-xl);
        border: 1px solid var(--border);
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
        gap: 0.75rem;
        align-items: center;
        justify-content: space-evenly;
        border: 1px solid var(--border);
    }

    .app-list .element img {
        width: 2rem;
        height: 2rem;
    }

    .app-list .element p {
        font-size: 12px;
        color: var(--muted-foreground);
    }

    .app-list .element .title {
        display: flex;
        gap: 0.5rem;
        align-items: center;
    }
</style>
<div class="navbar-main">
    <div class="start">
        <div class="mobile" style="display: none;">
            <DropdownMenu.Root>
                <DropdownMenu.Trigger style="display: flex"><icon.Menu size={20} /></DropdownMenu.Trigger>
                <DropdownMenu.Content>
                    <DropdownMenu.Group>
                        <a href="/#"><DropdownMenu.Item>Home</DropdownMenu.Item></a>
                        <a href="/#"><DropdownMenu.Item>Projects</DropdownMenu.Item></a>
                        <a href="/#"><DropdownMenu.Item>Tools</DropdownMenu.Item></a>
                    </DropdownMenu.Group>
                </DropdownMenu.Content>
            </DropdownMenu.Root>
        </div>
        <h2>Kleo08s</h2>
        <NavigationMenu.Root>
            <NavigationMenu.List>
                <NavigationMenu.Item >
                    <NavigationMenu.Link href="#"><b>Home</b></NavigationMenu.Link>
                </NavigationMenu.Item>
                <NavigationMenu.Item>
                    <NavigationMenu.Link href="#">Projects</NavigationMenu.Link>
                </NavigationMenu.Item>
                <NavigationMenu.Item>
                    <NavigationMenu.Link href="#">Tools</NavigationMenu.Link>
                </NavigationMenu.Item>
            </NavigationMenu.List>
        </NavigationMenu.Root>
    </div>
    <div class="end">
        <Popover.Root open={false}> <!-- * Remove after production -->
            <Popover.Trigger><icon.Grip style="cursor: pointer" /></Popover.Trigger>
            <Popover.Content class="w-130 rounded-[15px]" >
                <h3>Self-hosted Apps</h3>
                <p>Invite-only access to my self-hosted apps. DM me if you want to get access to them, but I accept only friends.</p>
                <div class="app-list" style="grid-template-columns: 1fr;">
                    <div class="element">
                        <img src="https://auth.kleo08s.lol/favicon.ico" alt="Logo">
                        <div style="width: 100%;">
                            <div class="title">
                                <b>Authelia</b>
                                <a href="https://kleo08s.instatus.com/" target="_blank" class={badgeVariants({ variant: "outline", class: "bg-green-700" })}><icon.BadgeCheck /></a>
                            </div>
                            <p>The main OAuth Provider</p>
                        </div>
                        <a href="https://auth.kleo08s.lol/"><icon.ExternalLink size=20 /></a>
                    </div>
                </div>
                <div class="app-list">
                    <div class="element">
                        <img src="https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fcf.appdrag.com%2Fdashboard-openvm-clo-b2d42c%2Fuploads%2FVaultwarden-yaX9.png&f=1&nofb=1&ipt=cbd3fd9fb825def153bd28bd2313cb5a2fad5e5f2e56e7217fe73a2958948687" alt="Logo">
                        <div style="width: 100%;">
                            <div class="title">
                                <b>BitWarden</b>
                                <a href="https://kleo08s.instatus.com/" target="_blank" class={badgeVariants({ variant: "outline", class: "bg-yellow-700" })}><icon.TriangleAlert /></a>
                            </div>
                            <p>Password manager</p>
                        </div>
                        <a href="https://vault.kleo08s.lol/"><icon.ExternalLink size=20 /></a>
                    </div>
                    <div class="element">
                        <img src="https://file.kleo08s.lol/api/favicon" alt="Logo">
                        <div style="width: 100%;">
                            <div class="title">
                                <b>Erugo</b>
                                <a href="https://kleo08s.instatus.com/" target="_blank" class={badgeVariants({ variant: "outline", class: "bg-yellow-700" })}><icon.TriangleAlert /></a>
                            </div>
                            <p>File sharing</p>
                        </div>
                        <a href="https://file.kleo08s.lol/"><icon.ExternalLink size=20 /></a>
                    </div>
                    <div class="element">
                        <img src="https://git.kleo08s.lol/assets/img/favicon.png" alt="Logo">
                        <div style="width: 100%;">
                            <div class="title">
                                <b>Gitea</b>
                                <a href="https://kleo08s.instatus.com/" target="_blank" class={badgeVariants({ variant: "outline", class: "bg-red-700" })}><icon.HeartCrack /></a>
                            </div>
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
