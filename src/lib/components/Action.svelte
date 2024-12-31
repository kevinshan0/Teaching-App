<script lang="ts">
    import * as Dialog from "$lib/components/ui/dialog";

    let props = $props();
</script>

<Dialog.Root>
    <Dialog.Trigger class="flex flex-row justify-between items-center w-full h-full">
        <div>
            <h1>{props.action}</h1>
        </div>
        <div>
            <h1>+</h1>
        </div>
    </Dialog.Trigger>
    
    <Dialog.Content>
        <Dialog.Header>
            <Dialog.Title>{props.action}</Dialog.Title>
                {#if props.action == "Plan Lessons"}
                    <Dialog.Description>
                        Schedule and plan a lesson.
                    </Dialog.Description>
                {:else if props.action == "Make Announcements"}
                    <Dialog.Description>
                        Make an announcement to subscribers of a class.
                    </Dialog.Description>
                {/if}
        </Dialog.Header>
    </Dialog.Content>
</Dialog.Root>
