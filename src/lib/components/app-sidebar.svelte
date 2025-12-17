<script lang="ts">
import { HouseIcon, BookMarked, Mail, ToolCase } from "@lucide/svelte";
import * as Sidebar from "$lib/components/ui/sidebar/index.js";
 
const items = [
    {
        title: "Home",
        url: "..",
        icon: HouseIcon,
    },
    {
        title: "Projects",
        url: "/projects",
        icon: BookMarked,
    },
    {
        title: "Contacts",
        url: "/contacts",
        icon: Mail,
    },
    {
        title: "Stuff",
        url: "/stuff",
        icon: ToolCase
    }
];
</script>
 
<Sidebar.Root style="padding-top: 3rem; margin-left: 10rem; border: none">
 <Sidebar.Content>
  <Sidebar.Group>
   <Sidebar.GroupLabel style="font-size: 1.75rem; font-family: var(--font-header)">Kleo08s</Sidebar.GroupLabel>
   <Sidebar.GroupContent>
    <Sidebar.Menu style="margin-top: 1rem">
     {#each items as item (item.title)}
      <Sidebar.MenuItem style="size: 4rem">
       <Sidebar.MenuButton>
        {#snippet child({ props })}
         <a href={item.url} {...props}>
          <item.icon />
          <span>{item.title}</span>
         </a>
        {/snippet}
       </Sidebar.MenuButton>
      </Sidebar.MenuItem>
     {/each}
    </Sidebar.Menu>
   </Sidebar.GroupContent>
  </Sidebar.Group>
 </Sidebar.Content>
</Sidebar.Root>