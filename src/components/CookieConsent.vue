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
			<a href="#" class="cookie-policy">Cookie Policy</a>.
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
	color: $white-color;
	font-size: $h3-fontsize;
	z-index: 4;
	padding: 5px 15px;
	border-radius: 5px;
	margin-left: 20px;
}

p {
	margin: 10px;
	max-width: 90%;
	font-size: $body-fontsize;
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
	width: 275px;
	height: 35px;
	font-family: $secondary-font;
}

.reject-btn {
	background-color: $emerald-color;
	color: white;
	&:hover {
		background-color: $white-color;
		color: rgba($emerald-color, 0.9);
		border: 2px solid $emerald-color;
		transform: scale(1.1);
	}
}

.accept-btn {
	background-color: $forest-color;
	color: white;
	&:hover {
		background-color: $white-color;
		color: rgba($forest-color, 0.9);
		border: 2px solid $forest-color;
		transform: scale(1.1);
	}
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
