<template>
	<div
		@dblclick="$emit('toggleReminder', task.id)"
		:class="[task.reminder ? 'reminder' : '', 'task']"
	>
		<h3>
			{{ task.text }}
			<i @click="$emit('delete-task', task.id)" class="fas fa-times"></i>
		</h3>
		<p>{{ formatDate(task.day) }}</p>
	</div>
</template>

<script>
const dayjs = require("dayjs");

export default {
	// eslint-disable-next-line vue/multi-word-component-names
	name: "Task",
	props: {
		task: Object,
	},
	methods: {
		formatDate(date) {
			return dayjs(date).format("MMMM DD, YYYY @ hh:MM A");
		},
	},
};
</script>

<style scope>
.fas {
	color: red;
}
.task {
	background: #f4f4f4;
	margin: 5px;
	padding: 10px 20px;
	cursor: pointer;
}
.task.reminder {
	border-left: 5px solid green;
}
.task h3 {
	display: flex;
	align-items: center;
	justify-content: space-between;
}
</style>
