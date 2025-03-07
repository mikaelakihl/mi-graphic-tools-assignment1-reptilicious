<template>
	<header class="header-mobile">
		<MenuIcon />
	</header>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import MenuIcon from '../components/atoms/MenuIcon.vue';

export default defineComponent({
	name: 'HeaderMobile',
	components: {
		MenuIcon,
	},
});
</script>

<style lang="scss" scoped>
.header-mobile {
	width: 100%;
	padding: 1rem;
	display: flex;
	justify-content: flex-end;
	background-color: transparent;
}
</style>
