<script lang="ts">
	import '../app.css';

    import * as Sidebar from "$lib/components/ui/sidebar/index.js";
    import AppSidebar from "$lib/components/app-sidebar.svelte";
    import { ModeWatcher } from 'mode-watcher';

	let { children } = $props();
</script>

<Sidebar.Provider>
    <AppSidebar />
    <Sidebar.Inset>
        <main>
            <ModeWatcher />
            {@render children?.()}
        </main>
    </Sidebar.Inset>
</Sidebar.Provider>
