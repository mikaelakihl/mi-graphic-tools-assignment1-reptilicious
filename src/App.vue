<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router';
import MainFooter from '@/fixtures/MainFooter.vue';
</script>

<template>
	<RouterLink to="/">Home</RouterLink>
	<RouterLink to="product">Products</RouterLink>
	<RouterLink to="about">About</RouterLink>

	<RouterView />
	<MainFooter />
</template>

<style lang="scss">

body {
	background-image: url(src/assets/images/reptilicious_backgroundimg_phone_1.png);
	background-position: top;
	background-size: cover;
	max-width: 100%;
	overflow-x: hidden;
	position: relative;
	min-height: 100vh;
}

@media screen and (min-width: 1280px) {
	body {
		background-image: url(src/assets/images/reptilicious_backgroundimg_desktop_1.jpg);
	}
}

</style>
