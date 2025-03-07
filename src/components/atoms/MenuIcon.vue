<template>
	<div class="menu-icon">
		<span class="menu-text">menu</span>
		<div class="menu-lines">
			<div class="line top"></div>
			<div class="line middle"></div>
			<div class="line bottom"></div>
		</div>
	</div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
	name: 'MenuIcon',
});
</script>

<style lang="scss" scoped>
.menu-icon {
	width: 4.78844rem;
	height: 3.4375rem;
	display: flex;
	flex-direction: column;
	align-items: center;
	justify-content: center;
	position: relative;
}

.menu-text {
	font-size: 1.2rem;
	color: #ffe552;
	position: absolute;
	top: 50%;
	transform: translateY(-50%);
}

.menu-lines {
	display: flex;
	flex-direction: column;
	gap: 0.5rem;
	position: absolute;
	width: 100%;
	height: 100%;
}

.line {
	width: 100%;
	height: 0.3rem;
	background-color: #ffe552;
}

.middle {
	background-color: #fbae29;
}
</style>
