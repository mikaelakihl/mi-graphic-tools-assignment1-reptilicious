<script setup lang="ts">
import { ref, onMounted } from 'vue';

// State to track visibility
const showBanner = ref(true);

// Check if user has already made a choice
onMounted(() => {
	const userChoice = localStorage.getItem('cookieConsent');
	if (userChoice) {
		showBanner.value = false; // Hide if already accepted/rejected
	}
});

// Handle user choices
const acceptCookies = () => {
	localStorage.setItem('cookieConsent', 'accepted');
	showBanner.value = false;
};

const rejectCookies = () => {
	localStorage.setItem('cookieConsent', 'rejected');
	showBanner.value = false;
};
</script>

<template>
	<div v-if="showBanner" class="cookie-banner">
		<h2 class="cookie-title">COOKIES</h2>
		<p>
			This website utilises technologies such as cookies to enable essential site functionality, as well as for
			analytics, personalisation, and targeted advertising purposes. You may change your setting at any time or accept
			the default settings.
			<a href="https://commission.europa.eu/cookies-policy_en" class="cookie-policy">Cookie Policy</a>.
		</p>
		<div class="button-container">
			<button class="reject-btn" @click="rejectCookies">Reject All</button>
			<button class="accept-btn" @click="acceptCookies">Accept All</button>
		</div>
	</div>
</template>

<style lang="scss" scoped>
.cookie-banner {
	position: fixed;
	bottom: 0;
	background-color: $orange-color;
	color: $black-color;
	padding: 20px;
	text-align: center;
	font-family: $secondary-font;
	box-shadow: 0px -2px 4px rgba(0, 0, 0, 0.2);
	z-index: 3;
	width: 100%;
	display: flex;
	flex-direction: column;
	align-items: center;
	gap: 10px;
}

.cookie-title {
	position: absolute;
	top: -20px;
	left: 0;
	transform: translateX(-20%);
	font-family: $primary-font;
	text-transform: uppercase;
	color: $white-color;
	font-size: 2rem;
	z-index: 4;
	padding: 5px 15px;
	border-radius: 5px;
	margin-left: 20px;
}

p {
	font-size: 14px;
	margin-bottom: 15px;
	max-width: 90%;
}

.cookie-policy {
	font-weight: bold;
	text-decoration: underline;
	color: $black-color;
}

.button-container {
	display: flex;
	flex-direction: column;
	align-items: center;
	gap: 10px;
	width: 100%;
}

button {
	padding: 10px 15px;
	border: none;
	border-radius: 25px;
	cursor: pointer;
	font-weight: bold;
	width: 275px;
	height: 35px;
}

.reject-btn {
	background-color: $emerald-color;
	color: white;
}

.accept-btn {
	background-color: $forest-color;
	color: white;
}

@media (min-width: 768px) {
	.cookie-banner {
		width: 350px;
		position: fixed;
		bottom: 20px;
		right: 20px;
		padding: 15px;
	}

	.cookie-title {
		top: -20px;
		left: 20px;
		transform: translateX(-30%);
	}
}
</style>
