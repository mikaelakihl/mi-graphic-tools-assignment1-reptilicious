<script setup lang="ts">
import { ref, onMounted, onUnmounted } from 'vue';
import { RouterView } from 'vue-router';
import MainFooter from '@/fixtures/MainFooter.vue';
import HeaderMobile from '@/fixtures/HeaderMobile.vue';
import HeaderDesktop from '@/fixtures/HeaderDesktop.vue';
import CookieConsent from './components/CookieConsent.vue';

const isMobileOrTablet = ref(window.innerWidth < 1280);

const checkScreenSize = () => {
	isMobileOrTablet.value = window.innerWidth < 1280;
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
