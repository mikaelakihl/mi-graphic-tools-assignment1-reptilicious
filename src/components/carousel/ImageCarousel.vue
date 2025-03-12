<script setup lang="ts">
import { ref, computed } from 'vue';
import ImageCarouselArrows from './ImageCarouselArrows.vue';
import ImageCarouselDots from './ImageCarouselDots.vue';

import krokodilKobraBlue from '../../assets/images/krokodil_kobra_blue.jpg';
import krokodilKobraGreen from '../../assets/images/krokodil_kobra_green.jpg';
import krokodilKobraRed from '../../assets/images/krokodil_kobra_red.jpg';

const images = [krokodilKobraBlue, krokodilKobraGreen, krokodilKobraRed];

const altTexts = [
	"A predominantly blue candy bag labeled 'Reptilicious – Wildly Tasty!' featuring cartoon snakes and crocodiles surrounded by gummy candies.",
	"A predominantly green candy bag labeled 'Reptilicious – Wildly Tasty!' featuring cartoon snakes and crocodiles surrounded by gummy candies.",
	"A predominantly red candy bag labeled 'Reptilicious – Wildly Tasty!' featuring cartoon snakes and crocodiles surrounded by gummy candies.",
];

const currentIndex = ref(0);

const leftIndex = computed(() => (currentIndex.value - 1 + images.length) % images.length);
const rightIndex = computed(() => (currentIndex.value + 1) % images.length);
const isAnimating = ref(false);

function nextImage() {
	if (isAnimating.value) return;
	isAnimating.value = true;

	currentIndex.value = (currentIndex.value + 1) % images.length;
	console.log('Next image, currentIndex:', currentIndex.value);

	setTimeout(() => {
		isAnimating.value = false;
	}, 500);
}

function prevImage() {
	if (isAnimating.value) return;
	isAnimating.value = true;

	currentIndex.value = (currentIndex.value - 1 + images.length) % images.length;
	console.log('Previous image, currentIndex:', currentIndex.value);

	setTimeout(() => {
		isAnimating.value = false;
	}, 500);
}
</script>

<template>
	<div class="carousel">
		<div class="carousel-inner">
			<ImageCarouselArrows direction="left" @click="prevImage" />

			<div class="carousel-images">
				<img
					v-for="(image, index) in images"
					:key="index"
					:src="image"
					:class="[
						'carousel-image',
						{ left: index === leftIndex, center: index === currentIndex, right: index === rightIndex },
					]"
					:alt="altTexts[index]"
				/>
			</div>

			<ImageCarouselArrows direction="right" @click="nextImage" class="carousel-arrow right" />
		</div>
		<ImageCarouselDots :current="currentIndex" :total="images.length" />
	</div>
</template>

<style lang="scss" scoped>
.carousel {
	min-width: 350px;
	max-width: 600px;
	margin: 0 auto;
	padding: 20px;
	position: relative;
	display: flex;
	flex-direction: column;
	align-items: center;
}

/* img-container */
.carousel-images {
	display: flex;
	justify-content: center;
	align-items: center;
	position: relative;
	min-height: 50vw;
	width: 100%;
	min-width: 250px;
}

/* img */
.carousel-image {
	width: 80%;
	min-height: auto;
	border-radius: 8px;
	transition:
		transform 0.5s ease,
		opacity 0.5s ease;
	position: absolute;
}

/* Positioning of images */
.carousel-image.left {
	transform: translateX(-25%) scale(0.85);
	opacity: 0.7;
	z-index: 1;
}

.carousel-inner {
	width: 90%;
}

.carousel-image.center {
	transform: translateX(0) scale(1);
	opacity: 1;
	z-index: 2;
}

.carousel-image.right {
	transform: translateX(25%) scale(0.85);
	opacity: 0.7;
	z-index: 1;
}
</style>
