<script setup lang="ts">
import { RouterView } from 'vue-router';
import MainFooter from '@/fixtures/MainFooter.vue';
import HeaderMobile from '@/fixtures/HeaderMobile.vue';
import CookieConsent from './components/CookieConsent.vue';
</script>

<template>
	<HeaderMobile />
	<RouterView />
	<CookieConsent />
	<MainFooter />
</template>
