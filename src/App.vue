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

<style></style>
