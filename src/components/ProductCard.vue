<script lang="ts" setup>
import { defineProps } from 'vue';
const props = defineProps({
	cardHeader: { type: String, required: true },
	cardSubheader: { type: String, required: true },
	cardContent: { type: String, required: true },
	imgSrc: { type: String, required: true },
	imgAlt: { type: String, required: true },
});
</script>

<template>
	<article>
		<div class="img-container">
			<img src="{{ imgSrc }}" alt="{{ imgAlt }}" width="256" height="261" />
			<h2>{{ cardHeader }}</h2>
		</div>
	</article>
</template>
