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
			:cardHeader="'Taste the jungle'"
			:cardSubheader="'Here you can find all our crazy flavors!'"
			:cardContent="''"
		/>
		<div class="product-card-container">
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
		</div>
	</main>
</template>

<style lang="scss" scoped>
main {
	margin: 60px $small-margin;
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

.product-card-container {
	display: flex;
	flex-direction: column;
	gap: $small-margin;
}

@media screen and (min-width: $tablet-size) {
	main {
		margin: $large-margin;
	}

	.product-card-container {
		flex-direction: unset;
		flex-wrap: wrap;
	}

	.product-card {
		min-width: 48%;
	}
}
</style>
