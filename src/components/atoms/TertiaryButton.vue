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
	color: $orange-color;
	border: solid 3px $orange-color;
	border-radius: $button-border-radius;
	padding-inline: $small-margin;
	font-family: $primary-font;
	font-size: $h4-fontsize;
	text-transform: uppercase;
	filter: drop-shadow(rgba(0, 0, 0, 0.25) -4px 4px 4px);
}

button:hover {
	background-color: $forest-color;
	color: $aged-copper-color;
	border: solid 3px $aged-copper-color;
}

button:active {
	background-color: $orange-color;
	color: $forest-color;
	border: solid 3px $forest-color;
}
</style>
