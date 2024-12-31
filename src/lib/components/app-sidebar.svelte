<script lang="ts">
    import Calendar from "lucide-svelte/icons/calendar";
    import House from "lucide-svelte/icons/house";
    import Inbox from "lucide-svelte/icons/inbox";
    import Settings from "lucide-svelte/icons/settings";
    import * as Sidebar from "$lib/components/ui/sidebar/index.js";
	import DarkModeToggle from "./DarkModeToggle.svelte";
	import Separator from "./ui/separator/separator.svelte";
	import Action from "./Action.svelte";

    // Menu items.
    const items = [
      {
        title: "Dashboard",
        icon: House,
      },
      {
        title: "Inbox",
        icon: Inbox,
      },
      {
        title: "Calendar",
        icon: Calendar,
      },
    ];

    let actions = [
        "Plan Lessons",
        "Make Announcements",
    ]
  </script>
   
  <Sidebar.Root variant="inset">
    <Sidebar.Header>
        <a href="/">
            <h1 class="scroll-m-20 text-4xl font-extrabold tracking-tight lg:text-5xl">LOGO</h1>
        </a>
    </Sidebar.Header>

    <Separator />

    <Sidebar.Content>
        <Sidebar.Group>
            <Sidebar.GroupLabel>Pages</Sidebar.GroupLabel>
            <Sidebar.GroupContent>
                <Sidebar.Menu>
                    {#each items as item (item.title)}
                        <Sidebar.MenuItem>
                            <Sidebar.MenuButton>
                                {#snippet child({ props })}
                                    <a href="/{item.title.toLocaleLowerCase()}" {...props}>
                                        <item.icon/>
                                        <span>{item.title}</span>
                                    </a>
                                {/snippet}
                            </Sidebar.MenuButton>
                        </Sidebar.MenuItem>
                    {/each}
                </Sidebar.Menu>
            </Sidebar.GroupContent>
        </Sidebar.Group>
        <Sidebar.Group>
            <Sidebar.GroupLabel>Quick Action</Sidebar.GroupLabel>
            <Sidebar.GroupContent>
                <Sidebar.Menu>
                    {#each actions as action}
                        <Sidebar.MenuItem>
                            <Sidebar.MenuButton>
                                <Action {action}/>
                            </Sidebar.MenuButton>
                        </Sidebar.MenuItem>
                    {/each}
                </Sidebar.Menu>
            </Sidebar.GroupContent>
        </Sidebar.Group>
    </Sidebar.Content>

    <Separator />

    <Sidebar.Footer>
        <div class="grid grid-cols-2 place-content-between">
            <div>
                <DarkModeToggle />
            </div>
        </div>
    </Sidebar.Footer>
  </Sidebar.Root>