<script setup lang="ts">
const props = defineProps<{
	buttonLabel: string;
	type?: 'button' | 'submit' | 'reset';
}>();
</script>

<template>
	<button :type="type">
		{{ buttonLabel }}
	</button>
</template>

<style lang="scss" scoped>
button {
	background-color: $forest-color;
	color: $mustard-color;
	border: solid 3px $mustard-color;
	border-radius: $button-border-radius;
	padding-inline: $small-margin;
	font-family: $primary-font;
	font-size: $h4-fontsize;
	text-transform: uppercase;
	filter: drop-shadow(-4px 4px 4px rgba(0, 0, 0, 0.25));
	cursor: pointer;
}

button:hover {
	background-color: $forest-color;
	color: $aged-copper-color;
	border: solid 3px $aged-copper-color;
}

button:active {
	background-color: $mustard-color;
	color: $forest-color;
	border: solid 3px $forest-color;
}
</style>
