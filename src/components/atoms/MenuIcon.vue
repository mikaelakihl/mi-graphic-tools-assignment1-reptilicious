<script setup lang="ts">
import { ref } from 'vue';

const menuOpen = ref(false);

const toggleMenu = () => {
	menuOpen.value = !menuOpen.value;
};
</script>

<template>
	<button class="menu-icon" @click="toggleMenu">
		<div class="lines">
			<span class="line top-line" :class="{ open: menuOpen }"></span>
			<span class="line middle-line" :class="{ open: menuOpen }"></span>
			<span class="line bottom-line" :class="{ open: menuOpen }"></span>
		</div>
		<span class="menu-text" :class="{ hidden: menuOpen }">menu</span>
	</button>
	<div class="menu-overlay" :class="{ open: menuOpen }">
		<nav class="menu">
			<a href="#">Home</a>
			<a href="#">Products</a>
			<a href="#">About Us</a>
		</nav>
	</div>
</template>

<style lang="scss" scoped>
.menu-icon {
	position: relative;
	width: 4.8rem;
	height: 3.5rem;
	display: flex;
	align-items: center;
	justify-content: center;
	border: none;
	background: none;
	cursor: pointer;
	padding: 0;
}

.line {
	position: absolute;
	max-width: 4rem;
	height: 0.4rem;
	display: block;
	left: 0;
}

.top-line {
	background-color: #ffe552;
	width: 3.8rem;
	top: 42%;
	transform: rotate(7deg) translateY(-1rem);
}

.middle-line {
	background-color: #fbae29;
	width: 3.9rem;
	top: 45%;
	transform: rotate(-5deg) translateY(0.2rem);
	z-index: -1;
}

.bottom-line {
	background-color: #ffe552;
	width: 100%;
	top: 52%;
	transform: rotate(2deg) translateY(1rem);
}

.menu-text {
	font-size: 0.97rem;
	font-weight: lighter;
	color: #ffe552;
	position: absolute;
	top: 20%;
	left: 0;
	transform: rotate(-1deg) translateY(0.1rem);
	z-index: 1;
}

/* menu style */
.menu-overlay {
	position: fixed;
	top: 1rem;
	left: 1rem;
	right: 1rem;
	bottom: 1rem;
	background: #056a55;
	border-radius: 10px;
	display: flex;
	flex-direction: column;
	justify-content: center;
	align-items: center;
	transition: transform 0.5s ease-in-out;
	transform: translateY(-100%);
	z-index: 10;
}

/* menu open */
.menu-overlay.open {
	transform: translateY(0);
}

/* menu-links */
.menu {
	display: flex;
	flex-direction: column;
	gap: 4rem;
}

.menu a {
	font-family: 'Spicy Rice', sans-serif;
	font-size: 3rem;
	color: #ffe552;
	text-transform: uppercase;
	text-decoration: none;
	display: flex;
	justify-content: center;
	align-items: center;
}

.menu a:hover {
	color: #fbae29;
}
</style>
