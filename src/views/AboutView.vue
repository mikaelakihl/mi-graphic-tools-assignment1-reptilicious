<script setup lang="ts">
import SmallCard from '../components/SmallCard.vue';
import PrimaryButton from '../components/atoms/PrimaryButton.vue';
import SecondaryButton from '../components/atoms/SecondaryButton.vue';
</script>

<template>
	<section class="about-view">
		<h1>About us</h1>

		<div class="about-content-container">
			<SmallCard
				cardHeader="Our story"
				cardSubheader="Wildly Inspired"
				cardContent="At Reptilicious, we draw inspiration from the wild heart of the jungle. Our candy brand is designed for those who crave adventure in every bite. From the lush, vibrant jungles to the mysterious creatures that call it home, we’ve created bold, unforgettable flavors that reflect the spirit of the wild. Each candy is crafted to take you on a flavorful journey, bringing you closer to nature’s untamed beauty. Join us and taste the adventure!"
			/>
			<SmallCard
				cardHeader="Our commitment"
				cardSubheader="Eco-Friendly"
				cardContent="At Reptilicious, we believe in a world where nature and flavor go hand in hand. That’s why we’re dedicated to creating candies that not only taste amazing but are also kind to the environment. Our products are made with eco-friendly ingredients and sustainable packaging to reduce our footprint on the planet. We also treat our staff with the utmost respect, ensuring a positive and fair work environment. For us, it’s not just about candy—it’s about creating a better world for everyone."
			/>
		</div>
		<section class="contact-us-container">
			<h2>Contact us</h2>
			<form class="contact-form">
				<label class="first-name">
					<span class="label-span">First name</span>
					<input class="form-input" type="text" name="first-name" required />
				</label>
				<label class="last-name">
					<span class="label-span">Last name</span>
					<input class="form-input" type="text" name="last-name" required />
				</label>
				<label class="message">
					<span class="label-span">Message</span>
					<textarea class="form-input textarea" rows="5" name="message" required />
				</label>
				<div class="buttons-container">
					<PrimaryButton buttonLabel="Send" type="submit" />
					<SecondaryButton buttonLabel="Cancel" type="reset" />
				</div>
			</form>
		</section>
	</section>
</template>
