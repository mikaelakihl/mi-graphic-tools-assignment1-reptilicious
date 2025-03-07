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
		:cardSubHeader="'Sweet'"
		:cardContent="'Our famous cola flavored crocodiles!'"
	/>
</template>
