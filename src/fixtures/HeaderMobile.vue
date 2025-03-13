<script lang="ts" setup>
import { ref, computed } from 'vue';
import { useRoute } from 'vue-router';
import MenuIcon from '../components/atoms/MenuIcon.vue';

const route = useRoute();
const isHomePage = computed(() => route.name === 'home');

const menuOpen = ref(false);
const toggleMenu = () => {
	menuOpen.value = !menuOpen.value;
};
</script>

<template>
	<header class="header-mobile">
		<div class="r-logo" v-if="!isHomePage">
			<RouterLink to="/" aria-label="go to homepage">
				<svg width="40" height="38" viewBox="0 0 40 38" fill="none" xmlns="http://www.w3.org/2000/svg">
					<path
						d="M10.1645 3.37045L7.97717 3.67443L8.66563 4.88925L3.92445 5.91338L2.46193 6.22929L2.77418 7.6926L8.51115 34.5777L8.80007 35.9317L10.1728 35.752L16.3097 34.9486L17.7098 34.7653L17.6114 33.3567L17.1155 26.2608L17.6519 26.1544L23.347 33.9711L23.8398 34.6474L24.6742 34.5834L33.4536 33.9092L36.2499 33.6945L34.5189 31.4878L28.3212 23.5871C28.6547 23.448 28.9919 23.2919 29.3278 23.1224C30.5507 22.5049 31.8672 21.652 33.0785 20.61C35.4406 18.5782 37.6772 15.5777 37.553 11.9988C37.5467 10.7252 36.8186 8.57201 35.1778 6.59117L35.1501 6.5578L35.1206 6.52608C31.986 3.15828 27.3126 2.22088 22.8326 2.15126C18.9933 2.0916 15.0005 2.67139 11.7661 3.14105C11.2081 3.22207 10.6727 3.29982 10.1645 3.37045ZM19.5227 11.0487L19.5227 11.0487C20.0102 11.0605 20.4727 11.0818 20.9021 11.1274C21.2332 11.1626 21.7427 11.3042 21.9147 11.3948C22.6159 11.7642 22.9784 12.36 23.1666 13.4269C23.1743 13.4707 23.1845 13.6126 23.1671 13.8127C23.1497 14.0138 23.1152 14.1477 23.1014 14.1848L24.5079 14.7062L23.1014 14.1848C22.886 14.766 22.6441 15.1329 22.3727 15.4204C22.0866 15.7236 21.7149 15.9955 21.1485 16.3367C20.3608 16.8113 18.9343 17.4113 18.0776 17.605C17.6041 17.712 17.1252 17.807 16.6397 17.8937L16.3156 11.2608L16.7728 11.2023C16.7728 11.2023 16.7729 11.2023 16.7729 11.2023C17.5279 11.1057 18.7842 11.031 19.5227 11.0487Z"
						fill="url(#paint0_linear_172_2676)"
						stroke="black"
						stroke-width="3"
					/>
					<defs>
						<linearGradient
							id="paint0_linear_172_2676"
							x1="19.1559"
							y1="3.44121"
							x2="24.063"
							y2="33.9076"
							gradientUnits="userSpaceOnUse"
						>
							<stop offset="0.105" stop-color="#FFE552" />
							<stop offset="1" stop-color="#FBAE29" />
						</linearGradient>
					</defs>
				</svg>
			</RouterLink>
		</div>

		<MenuIcon :menuOpen="menuOpen" @toggle-menu="toggleMenu" :class="{ hidden: menuOpen }" />

		<div class="menu-overlay" :class="{ open: menuOpen }">
			<div class="menu-container">
				<nav class="menu">
					<div class="menu-title" @click="toggleMenu"><span class="title">close</span><span class="line"></span></div>
					<RouterLink to="/" @click="toggleMenu">Home</RouterLink>
					<RouterLink to="/product" @click="toggleMenu">Products</RouterLink>
					<RouterLink to="/about" @click="toggleMenu">About Us</RouterLink>
				</nav>
			</div>
		</div>
	</header>
</template>

<style lang="scss" scoped>
.header-mobile {
	width: 100%;
	min-height: 60px;
	margin-top: 1rem;
	display: flex;
	justify-content: flex-end;
	background-color: transparent;
	top: 0;
}

.r-logo {
	margin-top: 1rem;
	position: absolute;
	left: 5%;
}

.hidden {
	transition:
		opacity 0.6s ease-in-out,
		visibility 0.6s;
	opacity: 0;
}

.menu-container {
	background: $emerald-color;
	width: calc(100% - 60px);
	min-height: calc(100% - 60px);
	border-radius: $large-card-border-radius;
	display: relative;
	flex-direction: column;
	justify-content: center;
	align-items: center;
	padding: $medium-margin;
	position: fixed;
	transform-origin: top right;
	transform: scale(0);
	transition:
		transform 0.6s ease-in-out,
		opacity 0.5s ease-in-out;
	opacity: 0;
}

.menu-overlay.open .menu-container {
	transform: scale(1);
	opacity: 1;
}

.menu-overlay {
	position: fixed;
	inset: 0;
	width: 100vw;
	min-height: 100vh;
	backdrop-filter: blur(3px);
	display: flex;
	justify-content: center;
	align-items: center;
	visibility: hidden;
	opacity: 0;
	transition:
		opacity 0.6s ease-in-out,
		visibility 0.6s;
	z-index: 10;
}

.menu-overlay.open {
	opacity: 1;
	visibility: visible;
}

.menu-title {
	font-family: $secondary-font;
	font-size: $h4-fontsize;
	color: $mustard-color;
	position: relative;
	display: flex;
	flex-direction: column;
	align-items: flex-start;
}

.title {
	cursor: pointer;
}

.menu-title .line {
	background-color: $orange-color;
	display: block;
	flex-direction: column;
	width: 5rem;
	min-height: 0.4rem;
	margin-top: 4px;
}

.menu {
	display: flex;
	flex-direction: column;
	gap: 6rem;
	text-align: center;
}

.menu a {
	font-family: $primary-font;
	font-size: $h1-fontsize;
	color: $mustard-color;
	text-transform: uppercase;
	text-decoration: none;
}

.menu a:hover {
	color: $orange-color;
}
</style>
