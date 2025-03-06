<script setup lang="ts">
import SecondaryButton from '@/components/atoms/SecondaryButton.vue';
import SmallCard from '@/components/SmallCard.vue';
</script>

<template>
	<div class="home-view">
		<figure>
			<img
				src="@/assets/images/reptilicious-logo.png"
				width="372"
				height="326"
				loading="lazy"
				alt="a waving green crocodile and a green snake that looks happy below a text that says retilicious"
			/>
		</figure>
		<section>
			<h1>Welcome Reptiles</h1>
			<span>Explore a World of Flavors</span>
		</section>
		<div>
			<!-- <Carousel /> -->
			<SecondaryButton />
			<!-- TODO: Add props to change label for button to: "All flavors" -->
			<SmallCard cardHeader="Reptilicious" cardSubheader="Wildly Delicious" cardContent="Unleash your inner adventurer with Reptilicious! Our jungle-inspired candies deliver bold, unforgettable flavors that take you on a wild ride. Whether you crave sweetness, saltiness, or sourness, every bite is a journey into the heart of the wild. Get ready to snack like never before!" />
		</div>
	</div>
</template>

<style lang="scss" scoped>

h1 {
	font-family: $primary-font;
	font-size: $h1-fontsize;
}

</style>
