<script setup lang="ts">
import SmallCard from '../components/SmallCard.vue';
import PrimaryButton from '../components/atoms/PrimaryButton.vue';
import SecondaryButton from '../components/atoms/SecondaryButton.vue';
</script>

<template>
	<main>
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
	</main>
</template>

<style lang="scss" scoped>
// Keep main and h1 in scoped CSS, move the rest to main.scss
main {
	gap: $medium-margin;
	margin: $small-margin;
	margin-bottom: 0;

	// ----- Keep above -------------------
	.about-content-container {
		display: flex;
		flex-direction: column;
		gap: $small-margin;
		margin-bottom: 10rem;
	}
	.contact-us-container {
		min-width: 100%;
		display: flex;
		flex-direction: column;
		align-items: center;
		gap: $small-margin;
		margin-bottom: 10rem;
		h2 {
			font-size: $h2-fontsize;
			color: $mustard-color;
		}
	}
	.contact-form {
		min-width: 100%;
		background-color: $emerald-color;
		display: flex;
		flex-direction: column;
		gap: $small-margin;
		padding: $small-margin;
		border-radius: $small-card-border-radius;
		filter: drop-shadow(rgba(0, 0, 0, 0.25) -4px 4px 4px);
		label {
			display: flex;
			flex-direction: column;
			gap: 0.25rem;
		}
		.label-span {
			font-family: $primary-font;
			font-size: $h4-fontsize;
			color: $mustard-color;
			filter: drop-shadow(rgba(0, 0, 0, 0.25) -4px 4px 4px);
		}
		.form-input {
			padding: 0.5rem;
			border-radius: $input-field-border-radius;
			border: none;
			font-family: $secondary-font;
			font-size: $body-fontsize;
		}
		.buttons-container {
			display: flex;
			justify-content: center;
			gap: $small-margin;
			button {
				flex: 1;
			}
		}
	}
}

@media screen and (min-width: $tablet-size) {
	main {
		display: grid;
		grid-template-columns: repeat(6, 1fr);
		column-gap: $small-margin;
		margin-inline: $large-margin;
		h1 {
			grid-column: span 6;
			text-align: center;
		}
		.about-content-container {
			grid-column: span 3;
		}
		.contact-us-container {
			grid-column: span 3;
			// height: 100%;
		}
	}
}

@media screen and (min-width: $desktop-size) {
	main {
		display: grid;
		grid-template-columns: repeat(12, 1fr);
		column-gap: $small-margin;
		margin-inline: $small-margin;
		h1 {
			grid-column: span 12;
			text-align: center;
			visibility: hidden; // TODO: Alternativt display: none om den istället ska finnas i headern
		}
		.about-content-container {
			grid-column: 3 / span 3;
		}
		.contact-us-container {
			grid-column: 8 / span 3;
		}
	}
}
</style>
