<script lang="ts">
    import * as Card from "$lib/components/ui/card";
    import * as Table from "$lib/components/ui/table";

    type payment = {
        date: Date,
        email: string,
        amount: number
    }

    let payments: payment[] = [
        {
            date: new Date(),
            email: "kevinshan@gmail.com",
            amount: 250.00
        }
    ]
</script>

<Card.Root class="h-full">
    <Card.Header>
        <Card.Title>Recent Payments</Card.Title>
        <Card.Description>See who has paid you.</Card.Description>
    </Card.Header>
    <Card.Content>
        <Table.Root>
            <Table.Caption>List of recent payments.</Table.Caption>
            <Table.Header>
                <Table.Row>
                    <Table.Head class="w-[100px]">Date</Table.Head>
                    <Table.Head>Email</Table.Head>
                    <Table.Head class="text-right">Amount</Table.Head>
                </Table.Row>
            </Table.Header>
            <Table.Body>
                {#each payments as payment}
                    <Table.Row>
                        <Table.Cell>{payment.date.getMonth()}/{payment.date.getDate()}</Table.Cell>
                        <Table.Cell>{payment.email}</Table.Cell>
                        <Table.Cell class="text-right">{payment.amount}</Table.Cell>
                    </Table.Row>
                {/each}
            </Table.Body>
        </Table.Root>
    </Card.Content>
</Card.Root>