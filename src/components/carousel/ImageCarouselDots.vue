<template>
	<div class="carousel-dots">
		<span v-for="index in total" :key="index" :class="['dot', { active: index - 1 === current }]"></span>
	</div>
</template>

<script setup lang="ts">
defineProps<{
	current: number;
	total: number;
}>();
</script>

<style lang="scss" scoped>
@use '@/styles/variables' as *;

.carousel-dots {
	display: flex;
	justify-content: center;
	background-color: $grey-color;
	padding: 5px 0;
	border-radius: 25px;
	margin-top: 50px;
}

.dot {
	width: 10px;
	height: 10px;
	background-color: $aged-copper-color;
	border-radius: 50%;
	margin: 0 5px;
	cursor: pointer;
}

.dot.active {
	background-color: $mustard-color;
}
</style>
