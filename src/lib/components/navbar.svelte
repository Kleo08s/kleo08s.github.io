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
                        <a href="/#"><DropdownMenu.Item><icon.House style="color: var(--foreground)"/><b>Home</b></DropdownMenu.Item></a>
                        <a href="/#"><DropdownMenu.Item><icon.BookMarked style="color: var(--muted-foreground)" />Projects</DropdownMenu.Item></a>
                        <a href="/#"><DropdownMenu.Item><icon.Wrench style="color: var(--muted-foreground)" />Tools</DropdownMenu.Item></a>
                    </DropdownMenu.Group>
                </DropdownMenu.Content>
            </DropdownMenu.Root>
        </div>
        <h2>Kleo08s</h2>
        <NavigationMenu.Root>
            <NavigationMenu.List>
                <NavigationMenu.Item >
                    <NavigationMenu.Link href="#">
                        <div style="display: flex; align-items: center; gap: 0.5rem;">
                            <icon.House style="color: var(--foreground)"/>
                            <b>Home</b>
                        </div>
                    </NavigationMenu.Link>
                </NavigationMenu.Item>
                <NavigationMenu.Item>
                    <NavigationMenu.Link href="#">
                        <div style="display: flex; align-items: center; gap: 0.5rem;">
                            <icon.BookMarked style="color: var(--muted-foreground)" />
                            <p>Projects</p>
                        </div>
                    </NavigationMenu.Link>
                </NavigationMenu.Item>
                <NavigationMenu.Item>
                    <NavigationMenu.Link href="#">
                        <div style="display: flex; align-items: center; gap: 0.5rem;">
                            <icon.Wrench style="color: var(--muted-foreground)" />
                            <p>Tools</p>
                        </div>
                    </NavigationMenu.Link>
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
        <Button href="https://kleo08s.lol/discord" target="_blank"><svg role="img" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><title>Discord</title><path d="M20.317 4.3698a19.7913 19.7913 0 00-4.8851-1.5152.0741.0741 0 00-.0785.0371c-.211.3753-.4447.8648-.6083 1.2495-1.8447-.2762-3.68-.2762-5.4868 0-.1636-.3933-.4058-.8742-.6177-1.2495a.077.077 0 00-.0785-.037 19.7363 19.7363 0 00-4.8852 1.515.0699.0699 0 00-.0321.0277C.5334 9.0458-.319 13.5799.0992 18.0578a.0824.0824 0 00.0312.0561c2.0528 1.5076 4.0413 2.4228 5.9929 3.0294a.0777.0777 0 00.0842-.0276c.4616-.6304.8731-1.2952 1.226-1.9942a.076.076 0 00-.0416-.1057c-.6528-.2476-1.2743-.5495-1.8722-.8923a.077.077 0 01-.0076-.1277c.1258-.0943.2517-.1923.3718-.2914a.0743.0743 0 01.0776-.0105c3.9278 1.7933 8.18 1.7933 12.0614 0a.0739.0739 0 01.0785.0095c.1202.099.246.1981.3728.2924a.077.077 0 01-.0066.1276 12.2986 12.2986 0 01-1.873.8914.0766.0766 0 00-.0407.1067c.3604.698.7719 1.3628 1.225 1.9932a.076.076 0 00.0842.0286c1.961-.6067 3.9495-1.5219 6.0023-3.0294a.077.077 0 00.0313-.0552c.5004-5.177-.8382-9.6739-3.5485-13.6604a.061.061 0 00-.0312-.0286zM8.02 15.3312c-1.1825 0-2.1569-1.0857-2.1569-2.419 0-1.3332.9555-2.4189 2.157-2.4189 1.2108 0 2.1757 1.0952 2.1568 2.419 0 1.3332-.9555 2.4189-2.1569 2.4189zm7.9748 0c-1.1825 0-2.1569-1.0857-2.1569-2.419 0-1.3332.9554-2.4189 2.1569-2.4189 1.2108 0 2.1757 1.0952 2.1568 2.419 0 1.3332-.946 2.4189-2.1568 2.4189Z"/></svg>Discord Server</Button>
    </div>
</div>