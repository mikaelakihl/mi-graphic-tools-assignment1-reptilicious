<script setup lang="ts">
import PrimaryButton from '@/components/atoms/PrimaryButton.vue';
import SecondaryButton from '@/components/atoms/SecondaryButton.vue';
</script>

<template>
	<h1>Home</h1>
	<PrimaryButton />
	<SecondaryButton />
</template>

<style lang="scss" scoped>

h1 {
	font-family: $primary-font;
	font-size: $h1-fontsize;
}

</style>