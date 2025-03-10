<script setup lang="ts">
import { ref, onMounted, onUnmounted } from 'vue';
import { RouterView } from 'vue-router';
import MainFooter from '@/fixtures/MainFooter.vue';
import HeaderMobile from '@/fixtures/HeaderMobile.vue';
import HeaderDesktop from '@/fixtures/HeaderDesktop.vue';
import CookieConsent from './components/CookieConsent.vue';

const isMobileOrTablet = ref(window.innerWidth < 1024);

const checkScreenSize = () => {
	isMobileOrTablet.value = window.innerWidth < 1024;
};

onMounted(() => {
	window.addEventListener('resize', checkScreenSize);
});

onUnmounted(() => {
	window.removeEventListener('resize', checkScreenSize);
});
</script>

<template>
	<div>
		<HeaderMobile v-if="isMobileOrTablet" />
		<HeaderDesktop v-else />
	</div>

	<RouterView />
	<CookieConsent />
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
