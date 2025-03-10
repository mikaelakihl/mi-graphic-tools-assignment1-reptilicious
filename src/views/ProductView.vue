<script lang="ts" setup>
import ProductCard from '../components/ProductCard.vue';
import SmallCard from '../components/SmallCard.vue';
import krokodileImageGreen from '../assets/images/krokodil_kobra_green.jpg';
import krokodileImageBlue from '../assets/images/krokodil_kobra_blue.jpg';
import krokodileImageRed from '../assets/images/krokodil_kobra_red.png';
</script>

<template>
	<main>
		<h1>Products</h1>
		<SmallCard
			class="small-card"
			:cardHeader="'Taste the jungle'"
			:cardSubheader="'Here you can find all our crazy flavors!'"
			:cardContent="''"
		/>
		<ProductCard
			:imgSrc="krokodileImageGreen"
			:imgAlt="'A bunch of happy reptiles in a green jungle'"
			:cardHeader="'Cuban Crocodiles'"
			:cardSubheader="'Sweet'"
			:cardContent="'Our famous cola flavored crocodiles!'"
		/>
		<ProductCard
			:imgSrc="krokodileImageRed"
			:imgAlt="'A bunch of happy reptiles in a red jungle'"
			:cardHeader="'King Cobras'"
			:cardSubheader="'Sour'"
			:cardContent="'Nothing beats the king!'"
		/>
		<ProductCard
			:imgSrc="krokodileImageBlue"
			:imgAlt="'A bunch of happy reptiles in a blue jungle'"
			:cardHeader="'Lizard Sizzle'"
			:cardSubheader="'Salty'"
			:cardContent="'These lizards are sizzling!'"
		/>
	</main>
</template>

<style lang="scss" scoped>
main {
	margin: 60px $small-margin 0;
	display: flex;
	flex-direction: column;
	align-items: center;
	gap: $small-margin;
}
h1 {
	font-family: $primary-font;
	font-size: $h1-fontsize;
	color: $mustard-color;
}

article {
	min-width: 100%;
}

article:last-of-type {
	margin-bottom: $large-margin;
}

@media screen and (min-width: $tablet-size) {
	main {
		margin: $large-margin;
		margin-bottom: 0;
		display: grid;
		grid-template-columns: repeat(6, 1fr);
		column-gap: $small-margin;
	}
	h1 {
		grid-column: span 6;
		text-align: center;
	}
	.small-card {
		grid-column: span 6;
	}

	.product-card {
		grid-column: span 3;
	}
	article:last-of-type {
		margin-bottom: 10rem;
	}
}

@media screen and (min-width: $desktop-size) {
	main {
		margin-left: 120px;
		margin-right: 120px;
		display: grid;
		grid-template-columns: repeat(12, 1fr);
		column-gap: $large-margin;
	}

	h1 {
		grid-column: span 12;
	}

	.small-card {
		margin-bottom: $small-margin;
		grid-column: span 12;
	}

	.product-card {
		grid-column: span 4;
	}
	article:last-of-type {
		margin-bottom: 0;
	}
}
</style>
