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
	<article class="product-card">
		<div class="img-container">
			<img :src="imgSrc" :alt="imgAlt" width="256" height="261" />
		</div>
		<h2>{{ cardHeader }}</h2>
		<span>{{ cardSubheader }}</span>
		<p>{{ cardContent }}</p>
		<PrimaryButton buttonLabel="Click" />
	</article>
</template>

<style lang="scss" scoped>
article {
	background-color: $white-color;
	padding: $small-margin;
	border-radius: 20px;
	display: flex;
	flex-direction: column;
	gap: $small-margin;
	min-width: 100%;
}
.img-container {
	height: auto;
	width: 100%;
	overflow: hidden;
}

img {
	width: 100%;
	height: 100%;
	object-fit: cover;
}

h2 {
	font-family: $primary-font;
	font-size: $h3-fontsize;
	color: $forest-color;
	text-transform: uppercase;
}

span,
p {
	font-family: $secondary-font;
	color: $forest-color;
}

span {
	font-size: $subhead-fontsize;
}

button {
	width: 60%;
}

@media screen and (min-width: $tablet-size) {
	article {
		min-width: 335px;
		min-height: 568px;
	}
}
</style>
