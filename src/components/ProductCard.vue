<script lang="ts" setup>
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
	height: auto;
	object-fit: cover;
}

h2 {
	font-size: $h3-fontsize;
	color: $forest-color;
}

span,
p {
	font-family: $secondary-font;
	color: $forest-color;
}

span {
	font-size: $subhead-fontsize;
	font-weight: $font-weight-medium;
}

button {
	width: 60%;
}
</style>
