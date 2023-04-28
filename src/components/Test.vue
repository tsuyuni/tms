<script setup lang="ts">
interface Props {
	title: string;
	content: number;
}
defineProps<Props>();
</script>

<template>
	<section>
		<h1>{{title}}</h1>
		<p>{{content}}</p>
	</section>
</template>

<style scoped>
section {
	border: 1px solid red;
	width: 500px;
	height: 300px;
}

h1 {
/*	color: red;*/
}
</style>