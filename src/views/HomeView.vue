<script setup lang="ts">
import { onMounted, onUnmounted, ref } from 'vue';
import TertiaryButton from '../components/atoms/TertiaryButton.vue';
import ImageCarousel from '../components/carousel/ImageCarousel.vue';
import SmallCard from '../components/SmallCard.vue';

const isMobile = ref<boolean>(window.innerWidth <= 767);

function updateWindowResize(): void {
	isMobile.value = window.innerWidth <= 767;
}

function setupResizeListener(): void {
	window.addEventListener('resize', updateWindowResize);
}

function removeResizeListener(): void {
	window.removeEventListener('resize', updateWindowResize);
}

onMounted(setupResizeListener);
onUnmounted(removeResizeListener);
</script>

<template>
	<main>
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
			<div class="image-container">
				<ImageCarousel v-if="isMobile" />
				<div v-else class="image-displayer">
					<img src="@/assets/images/krokodil_kobra_blue.jpg" width="256" height="261" loading="lazy" />
					<img src="@/assets/images/krokodil_kobra_green.jpg" width="256" height="261" loading="lazy" />
					<!-- TODO: Add alt-texts -->
					<img src="@/assets/images/krokodil_kobra_red.jpg" width="256" height="261" loading="lazy" />
					<!-- TODO: Change to ".png" -->
				</div>
			</div>
			<TertiaryButton buttonLabel="All flavors" type="button" @click="$router.push('product')" />
			<SmallCard
				cardHeader="Reptilicious"
				cardSubheader="Wildly Delicious"
				cardContent="Unleash your inner adventurer with Reptilicious! Our jungle-inspired candies deliver bold, unforgettable flavors that take you on a wild ride. Whether you crave sweetness, saltiness, or sourness, every bite is a journey into the heart of the wild. Get ready to snack like never before!"
			/>
		</div>
	</main>
</template>

<style lang="scss" scoped>
.heading-one-container {
	min-width: 100%;
	background-color: $white-color;
	text-align: center;
	padding-top: $small-margin;
	padding-bottom: $small-margin;
	h1 {
		font-size: $h3-fontsize;
		margin-bottom: 0.5rem;
		color: $forest-color;
	}
	span {
		font-size: $subhead-fontsize;
		font-weight: $font-weight-medium;
		color: $forest-color;
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

@media screen and (min-width: $tablet-size) {
	main {
		.content-container {
			margin-inline: $large-margin;
			margin-bottom: 10rem;
			position: relative;
		}
		.image-container {
			width: 100%;
			position: absolute;
		}
		.image-displayer {
			width: 100%;
			img:first-of-type {
				position: absolute;
				top: -8rem;
				right: -2rem;
				transform: rotate(35deg);
				height: 182px;
				width: auto;
			}
			img:nth-of-type(2) {
				position: absolute;
				top: -21rem;
				left: -2rem;
				transform: rotate(-10deg);
				height: 182px;
				width: auto;
			}
			img:last-of-type {
				position: absolute;
				top: 20rem;
				left: 2rem;
				transform: rotate(10deg);
				height: 182px;
				width: auto;
			}
		}
		.small-card-article {
			margin-bottom: 16rem;
		}
	}
}

@media screen and (min-width: $desktop-size) {
	main {
		.content-container {
			max-width: 35vw;
			img:first-of-type {
				position: absolute;
				top: -12rem;
				right: -17rem;
				transform: rotate(-12deg);
				height: 290px;
				width: auto;
				z-index: 1;
			}
			img:nth-of-type(2) {
				position: absolute;
				top: -21rem;
				left: -25rem;
				transform: rotate(-10deg);
				height: 359px;
				width: auto;
			}
			img:last-of-type {
				position: absolute;
				top: -20rem;
				left: auto;
				right: -27rem;
				transform: rotate(17deg);
				height: 290px;
				width: auto;
			}
		}
		.small-card-article {
			margin-bottom: 0;
		}
	}
}
</style>
