<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router';
</script>

<template>
	<RouterLink to="/">Home</RouterLink>
	<RouterLink to="product">Products</RouterLink>
	<RouterLink to="about">About</RouterLink>

	<RouterView />
</template>

<style lang="scss">

body {
	margin: 0;
	background-image: url(src/assets/images/reptilicious_backgroundimg_phone_1.png);
	background-position: top;
	background-size: cover;
}

</style>
