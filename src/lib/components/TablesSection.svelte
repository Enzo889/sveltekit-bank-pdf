<script lang="ts">
	import * as Table from '$lib/components/ui/table/index.js';

	const invoices = [
		{
			invoice: 'INV001',
			paymentStatus: 'Paid',
			totalAmount: '$250.00',
			paymentMethod: 'Credit Card'
		},
		{
			invoice: 'INV002',
			paymentStatus: 'Pending',
			totalAmount: '$150.00',
			paymentMethod: 'PayPal'
		},
		{
			invoice: 'INV003',
			paymentStatus: 'Unpaid',
			totalAmount: '$350.00',
			paymentMethod: 'Bank Transfer'
		},
		{
			invoice: 'INV004',
			paymentStatus: 'Paid',
			totalAmount: '$450.00',
			paymentMethod: 'Credit Card'
		},
		{
			invoice: 'INV005',
			paymentStatus: 'Paid',
			totalAmount: '$550.00',
			paymentMethod: 'PayPal'
		},
		{
			invoice: 'INV006',
			paymentStatus: 'Pending',
			totalAmount: '$200.00',
			paymentMethod: 'Bank Transfer'
		},
		{
			invoice: 'INV007',
			paymentStatus: 'Unpaid',
			totalAmount: '$300.00',
			paymentMethod: 'Credit Card'
		}
	];
</script>

<div
	id="Tables"
	class="mx-auto flex w-full max-w-xl flex-col items-center justify-center space-y-4 py-7"
>
	<h2 class="text-4xl font-bold">Tables Section</h2>
	<p class="text-pretty text-lg">This is the Tables section on the website</p>
	<Table.Root>
		<Table.Caption class="pt-4 text-muted-foreground">A list of your recent invoices.</Table.Caption
		>
		<Table.Header class="pt-4 text-muted-foreground">
			<Table.Row>
				<Table.Head class="w-[100px]">Invoice</Table.Head>
				<Table.Head>Status</Table.Head>
				<Table.Head>Method</Table.Head>
				<Table.Head class="text-right">Amount</Table.Head>
			</Table.Row>
		</Table.Header>
		<Table.Body>
			{#each invoices as invoice, i (i)}
				<Table.Row>
					<Table.Cell class="font-medium">{invoice.invoice}</Table.Cell>
					<Table.Cell>{invoice.paymentStatus}</Table.Cell>
					<Table.Cell>{invoice.paymentMethod}</Table.Cell>
					<Table.Cell class="text-right">{invoice.totalAmount}</Table.Cell>
				</Table.Row>
			{/each}
		</Table.Body>
	</Table.Root>
</div>
