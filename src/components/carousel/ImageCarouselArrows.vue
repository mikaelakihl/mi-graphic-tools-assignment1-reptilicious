<script setup lang="ts">
defineProps<{
	direction: 'left' | 'right';
}>();
</script>

<template>
	<button :class="['carousel-arrow', direction]" @click="$emit('click')">
		{{ direction === 'left' ? '←' : '→' }}
	</button>
</template>

<style lang="scss" scoped>

.carousel-arrow {
	position: absolute;
	top: 50%;
	transform: translateY(-50%);
	background-color: rgba($white-color, 0.9);
	color: $forest-color;
	border: 2px solid $forest-color;
	width: 50px;
	height: 50px;
	border-radius: 50%;
	justify-content: center;
	align-items: center;
	cursor: pointer;
	transition:
		background-color 0.3s ease,
		transform 0.3s ease;
	z-index: 3;

	&:hover {
		background-color: $emerald-color;
		color: rgba($white-color, 0.9);
		border: 2px solid $white-color;
		transform: translateY(-50%) scale(1.1);
	}
}

.carousel-arrow.left {
	left: 1%;
}

.carousel-arrow.right {
	right: 1%;
}

@media (max-width: 450px) {
	.carousel-images {
		height: 35vh;
	}

	.carousel-arrow {
		width: 40px;
		height: 40px;
	}

	.carousel-arrow.left {
		left: 1%;
	}

	.carousel-arrow.right {
		right: 1%;
	}
}
</style>
