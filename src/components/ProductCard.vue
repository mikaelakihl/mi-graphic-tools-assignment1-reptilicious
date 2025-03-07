<script lang="ts" setup>
import { defineProps } from 'vue';
import PrimaryButton from '../components/atoms/PrimaryButton.vue';

const props = defineProps<{
	cardHeader: string;
	cardSubheader: string;
	cardContent: string;
	imgSrc: string;
	imgAlt: string;
}>();
</script>

<template>
	<article>
		<div class="img-container">
			<img :src="imgSrc" :alt="imgAlt" width="256" height="261" />
		</div>
		<h2>{{ cardHeader }}</h2>
		<span>{{ cardSubheader }}</span>
		<p>{{ cardContent }}</p>
		<PrimaryButton buttonLabel="Click" />
	</article>
</template>

<style lang="scss" scoped></style>
