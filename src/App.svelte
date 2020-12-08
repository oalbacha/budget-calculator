<script>
	// components
	import Navbar from './Navbar.svelte'
	import Title from './Title.svelte'
	import expenseData from './expenses'
	import ExpensesList from './ExpensesList.svelte'
	import { setContext } from 'svelte'
	// variables
	let expenses = [...expenseData]
	// functions
	function removeExpense(id) {
		expenses = expenses.filter(expense => expense.id != id)
	}
	// context
	setContext('remove', removeExpense)
</script>

<style>
</style>

<Navbar />
<main class="content">
<ExpensesList {expenses} />
</main>