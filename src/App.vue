<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router';
</script>

<template>
	<RouterLink to="/">Home</RouterLink>
	<RouterLink to="product">Products</RouterLink>
	<RouterLink to="about">About</RouterLink>

	<RouterView />
</template>

<style></style>
