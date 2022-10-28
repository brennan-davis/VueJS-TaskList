<template>
	<header>
		<h1>{{ title }}</h1>
		<Button
			@toggle-add-task="$emit('toggle-add-task')"
			:text="showAddTasks ? 'Close' : 'Add Task'"
			:color="showAddTasks ? 'red' : 'green'"
		/>
	</header>
</template>

<script>
import Button from "./Button";

export default {
	// eslint-disable-next-line vue/multi-word-component-names
	name: "Header",
	props: {
		title: String,
		showAddTasks: Boolean,
	},
	components: {
		Button,
	},
};
</script>

<style scoped>
header {
	display: flex;
	justify-content: space-between;
	align-items: center;
	margin-bottom: 20px;
}
</style>
