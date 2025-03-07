<template>
	<div class="carousel">
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
				alt="Carousel image"
			/>
		</div>

		<ImageCarouselArrows direction="right" @click="nextImage" class="carousel-arrow right" />
		<ImageCarouselDots :current="currentIndex" :total="images.length" />
	</div>
</template>

<script setup lang="ts">
import { ref, computed } from 'vue';
import ImageCarouselArrows from './ImageCarouselArrows.vue';
import ImageCarouselDots from './ImageCarouselDots.vue';

import krokodilKobraBlue from '../../assets/images/krokodil_kobra_blue.jpg';
import krokodilKobraGreen from '../../assets/images/krokodil_kobra_green.jpg';
import krokodilKobraRed from '../../assets/images/krokodil_kobra_red.jpg';

// img list
const images = [krokodilKobraBlue, krokodilKobraGreen, krokodilKobraRed];

// Index for showed img
const currentIndex = ref(0);

// Calculate the index for the left and right images
const leftIndex = computed(() => (currentIndex.value - 1 + images.length) % images.length);
const rightIndex = computed(() => (currentIndex.value + 1) % images.length);

// function to change img
function nextImage() {
	currentIndex.value = (currentIndex.value + 1) % images.length;
}

function prevImage() {
	currentIndex.value = (currentIndex.value - 1 + images.length) % images.length;
}
</script>

<style lang="scss" scoped>
.carousel {
	max-width: 450px;
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
	height: 30vh;
	width: 100%;
	max-width: 400px;
}

/* img */
.carousel-image {
	width: 80%;
	height: auto;
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
