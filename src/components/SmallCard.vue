<script setup lang="ts">
const props = defineProps<{
	cardHeader: string;
	cardSubheader: string;
	cardContent: string;
}>();
</script>

<template>
	<article class="small-card-article">
		<h2>{{ cardHeader }}</h2>
		<span class="subheading">{{ cardSubheader }}</span>
		<p>{{ cardContent }}</p>
	</article>
</template>

<style lang="scss" scoped>
@use '@/styles/variables' as *;
article {
	background-color: $white-color;
	color: $forest-color;
	border-radius: $small-card-border-radius;
	display: flex;
	flex-direction: column;
	gap: 0.5rem;
	padding: $small-margin;
	filter: drop-shadow(-4px 4px 4px rgba(0, 0, 0, 0.25));
	h2 {
		font-size: $h3-fontsize;
	}
	.subheading {
		font-size: $subhead-fontsize;
		font-weight: $font-weight-medium;
	}
	p {
		font-family: $secondary-font;
		font-size: $body-fontsize;
	}
}
</style>
