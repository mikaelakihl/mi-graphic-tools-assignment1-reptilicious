<script setup lang="ts">
import { ref, computed } from 'vue';
import ImageCarouselArrows from './ImageCarouselArrows.vue';
import ImageCarouselDots from './ImageCarouselDots.vue';

import krokodilKobraBlue from '../../assets/images/krokodil_kobra_blue.jpg';
import krokodilKobraGreen from '../../assets/images/krokodil_kobra_green.jpg';
import krokodilKobraRed from '../../assets/images/krokodil_kobra_red.jpg';

// Array of images used in the carousel
const images = [krokodilKobraBlue, krokodilKobraGreen, krokodilKobraRed];

// Track the index of the currently displayed image
const currentIndex = ref(0);

// Compute the index of the left and right images for smooth transitions
const leftIndex = computed(() => (currentIndex.value - 1 + images.length) % images.length);
const rightIndex = computed(() => (currentIndex.value + 1) % images.length);

// Prevents spam clicking by locking animation until transition is complete
const isAnimating = ref(false);

/**
 * Moves to the next image in the carousel.
 * If at the last image, it loops back to the first one.
 */
function nextImage() {
	if (isAnimating.value) return; // Prevents multiple clicks during animation
	isAnimating.value = true;

	// Move to the next image or loop back to the first
	currentIndex.value = (currentIndex.value + 1) % images.length;
	console.log('Next image, currentIndex:', currentIndex.value);

	// Unlock animation after 500ms (same duration as CSS transition)
	setTimeout(() => {
		isAnimating.value = false;
	}, 500);
}

/**
 * Moves to the previous image in the carousel.
 * If at the first image, it loops back to the last one.
 */
function prevImage() {
	if (isAnimating.value) return;
	isAnimating.value = true;

	// Move to the previous image or loop back to the last
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
			<!-- Left arrow button to go to the previous image -->
			<ImageCarouselArrows direction="left" @click="prevImage" />

			<!-- Image container displaying the three main images -->
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

			<!-- Right arrow button to go to the next image -->
			<ImageCarouselArrows direction="right" @click="nextImage" class="carousel-arrow right" />
		</div>

		<!-- Dots to indicate the current image in the carousel -->
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

/* Positioning the left image (previous image) */
.carousel-image.left {
	transform: translateX(-25%) scale(0.85);
	opacity: 0.7;
	z-index: 1;
}

/* Ensures the carousel content is properly centered */
.carousel-inner {
	width: 90%;
}

/* Positioning the center image (currently active image) */
.carousel-image.center {
	transform: translateX(0) scale(1);
	opacity: 1;
	z-index: 2;
}

/* Positioning the right image (next image) */
.carousel-image.right {
	transform: translateX(25%) scale(0.85);
	opacity: 0.7;
	z-index: 1;
}
</style>
