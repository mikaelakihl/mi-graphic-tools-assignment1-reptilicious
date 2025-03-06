<script setup lang="ts">
import TertiaryButton from '@/components/atoms/TertiaryButton.vue';
import SmallCard from '@/components/SmallCard.vue';
</script>

<template>
	<div class="home-view">
		<figure>
			<img
				src="@/assets/images/reptilicious_logo.png"
				width="372"
				height="326"
				loading="lazy"
				alt="a waving green crocodile and a green snake that looks happy below a text that says retilicious"
			/>
		</figure>
		<section class="heading-one-container">
			<h1>Welcome Reptiles</h1>
			<span>Explore a World of Flavors</span>
		</section>
		<div class="content-container">
			<!-- <Carousel /> -->
			<TertiaryButton buttonLabel="All flavors" @click="$router.push('product')"/>
			<!-- TODO: Add props to change label for button to: "All flavors" -->
			<SmallCard
				cardHeader="Reptilicious"
				cardSubheader="Wildly Delicious"
				cardContent="Unleash your inner adventurer with Reptilicious! Our jungle-inspired candies deliver bold, unforgettable flavors that take you on a wild ride. Whether you crave sweetness, saltiness, or sourness, every bite is a journey into the heart of the wild. Get ready to snack like never before!"
			/>
		</div>
	</div>
</template>

<style lang="scss" scoped>
.home-view {
	max-width: 100vw;
	display: flex;
	flex-direction: column;
	align-items: center;
	.heading-one-container {
		min-width: 100%;
		background-color: $white-color;
		text-align: center;
		color: $forest-color;
		padding-top: $small-margin;
		padding-bottom: $small-margin;
		h1 {
			font-family: $primary-font;
			font-size: $h3-fontsize;
			text-transform: uppercase;
			margin-bottom: 0.5rem;
		}
		span {
			font-family: $secondary-font;
			font-size: $subhead-fontsize;
		}
	}
	.content-container {
		margin-top: $large-margin;
		margin-bottom: $large-margin;
		margin-inline: $small-margin;
		display: flex;
		flex-direction: column;
		align-items: center;
		gap: $large-margin;
	}
}

@media screen and (min-width: 800px) {
	.home-view {
		.content-container {
			margin-inline: $large-margin;
		}
	}
}

@media screen and (min-width: 1280px) {
	.home-view {
		.content-container {
			max-width: 35vw;
		}
	}
}
</style>
