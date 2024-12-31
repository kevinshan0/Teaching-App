<script lang="ts">
    import NextLesson from "$lib/components/NextLesson.svelte";
	import RecentPayments from "$lib/components/RecentPayments.svelte";
</script>

<div class="m-0 p-12 flex-col space-y-8">
    <h1>Dashboard</h1>
    <div class="grid grid-cols-3 gap-12 w-full">
        <div class="col-span-2">
            <NextLesson />
        </div>
        <div class="col-span-2">
            <RecentPayments />
        </div>
    </div>
</div>