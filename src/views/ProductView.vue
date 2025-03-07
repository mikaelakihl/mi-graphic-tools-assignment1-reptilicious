<script lang="ts" setup>
import ProductCard from '../components/ProductCard.vue';
import krokodileImageGreen from '../assets/images/krokodil_kobra_green.jpg';
import krokodileImageBlue from '../assets/images/krokodil_kobra_blue.jpg';
import krokodileImageRed from '../assets/images/krokodil_kobra_red.png';
</script>

<template>
	<h1>Products</h1>

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
</template>
