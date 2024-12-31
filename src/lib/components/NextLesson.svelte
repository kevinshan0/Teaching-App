<script lang="ts">
    import * as Card from "$lib/components/ui/card";
    import { Separator } from "$lib/components/ui/separator";
</script>

<Card.Root class="h-full">
    <Card.Header>
        <Card.Title>Your Next Lesson</Card.Title>
        <Card.Description>See when you next lesson is and what you have planned.</Card.Description>
    </Card.Header>
    <Card.Content>
        <div class="flex flex-row gap-x-4">
            <div class="flex flex-col gap-y-2 flex-auto w-1/5">
                <h1>Date and Time</h1>
                <div>
                    ...rest content
                </div>
            </div>

            <Separator orientation="vertical"/>

            <div class="flex flex-col gap-y-2 flex-auto w-4/5">
                <h1>Lesson Plan</h1>
                <div>
                    ...rest content
                </div>
            </div>
        </div>
    </Card.Content>
</Card.Root>