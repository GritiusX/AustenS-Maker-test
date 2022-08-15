<template>
	<nav class="navbar">
		<MakerIcon />
	</nav>
	<header class="main-header">
		<div class="sub-header">
			<h1 class="sub-title">
				Get paid for the work you <span class="colored-span">love</span> to do.
			</h1>
			<h3 class="sub-description">
				The 9-5 grind is so last century. We believe in living life on your own
				terms. Whether you're looking to escape the rat race or set up a side
				hustle, we've got you covered.
			</h3>
			<MouseSvg class="mouse-svg" />
		</div>
	</header>

	<main class="main-container">
		<section class="icons-section">
			<IconBox
				icon="egg"
				title="Indulge your passions"
				description="Your passions shouldn't be just for the weekend. Earn a living doing what you love."
			/>
			<IconBox
				icon="moneyjar"
				title="Gain financial freedom"
				description="Start making money work for you. There’s nothing quite like earning while you sleep. "
			/>
			<IconBox
				icon="cocktail"
				title="Choose your lifestyle"
				description="Own your daily schedule. Fancy a lie-in? Go for it! Take charge of your week."
			/>
			<IconBox
				icon="roadtrip"
				title="Work from anywhere"
				description="Selling online means not being pinned down. Want to work AND travel? Go for it!"
			/>
		</section>
		<section class="pricing-section">
			<h1 class="pricing-title">Our pricing plans</h1>
			<h3 class="pricing-description">
				We only make money when our creators make money. Our plans are always
				affordable, and it's completely free to get started.
			</h3>
			<div class="pricing-modals">
				<PriceModal
					title="Dip your toe"
					description="Just getting started? No problem at all! Our free plan will take you a long way."
					:checks="checks"
					price="Free"
				/>
				<PriceModal
					title="Dive right in"
					description="Ready for the big time? Our paid plan will help you take your business to the next level."
					:checks="checks2"
					price="25.00"
				/>
			</div>
		</section>
		<footer class="footer-section">
			<h3 class="footer-title">Get notified when we launch</h3>
			<div class="footer-buttons">
				<TextField
					class="footer-input-size"
					v-model.trim="emailInput"
					:error="error"
				/>
				<MButton
					class="footer-button-size"
					text="Get Notified"
					@click="validateEmail(emailInput)"
				/>
				{{ error }}
			</div>
		</footer>
	</main>
</template>
<!-- TO DO - Iconbox + PriceModal check svg so it changes through tablet + desktop -->
<script setup>
/* import HelloWorld from "./components/HelloWorld.vue"; */
import TextField from "./components/TextField.vue";
import MButton from "./components/MButton.vue";
import IconBox from "./components/IconBox.vue";
import PriceModal from "./components/PriceModal.vue";
import { ref } from "vue";
import MouseSvg from "./components/svg/MouseSvg.vue";
import MakerIcon from "./components/svg/MakerIcon.vue";

const checks = ref([
	"Unlimited products",
	"Basic analytics",
	"Limited marketplace exposure",
	"10% fee per transaction",
]);
const checks2 = ref([
	"Custom domain",
	"Advanced analytics and reports",
	"High marketplace visibility",
	"5% fee per transaction",
]);

const emailInput = ref("");
const error = ref(false);

const validateEmail = (value) => {
	if (/^\w+([\.-]?\w+)*@\w+([\.-]?\w+)*(\.\w{2,3})+$/.test(value)) {
		return (error.value = false);
	} else {
		return (error.value = true);
	}
};
</script>

<style lang="scss">
@import "./assets/variables";

.navbar {
	display: flex;
	justify-content: center;
	margin-top: 40px;
}
.main-header {
	background-image: url("./assets/FullBG.svg");
	background-repeat: no-repeat;
	background-size: contain;
	display: flex;
	justify-content: center;
	margin-top: 66px;
	padding: 0 24px;
	.sub-header {
		display: flex;
		flex-direction: column;
		margin-top: 283px;
		align-items: center;
		width: 100%;

		.sub-title {
			font-style: normal;
			font-weight: 800;
			font-size: 32px;
			line-height: 40px;
			text-align: center;
			word-spacing: 1px;
			padding: 0 36px;
			color: $white;
			margin-block-start: 0em;
			margin-block-end: 0em;
			.colored-span {
				font-style: normal;
				font-weight: 800;
				font-size: 32px;
				line-height: 40px;
				text-align: center;
				word-spacing: 1px;
				color: $light-blue;
			}
		}
		.sub-description {
			font-family: "Manrope";
			font-style: normal;
			font-weight: 500;
			font-size: 15px;
			line-height: 25px;
			text-align: center;
			color: $grey;
			z-index: 0;
			margin-top: 20px;
			margin-bottom: 32px;
		}
	}
}
.main-container {
	display: flex;
	flex-direction: column;
	justify-content: center;
	align-items: center;
	margin-top: 144px;
	margin-bottom: 164px;
	padding: 0 24px;
	row-gap: 144px;

	.icons-section {
		display: flex;
		flex-direction: column;
		row-gap: 56px;
	}
	.pricing-section {
		.pricing-title {
			font-family: Manrope;
			font-size: 24px;
			font-weight: 800;
			line-height: 33px;
			letter-spacing: 0px;
			text-align: center;
			color: $white;
		}
		.pricing-description {
			font-family: Manrope;
			font-size: 15px;
			font-weight: 500;
			line-height: 25px;
			letter-spacing: 0px;
			text-align: center;
			color: $grey;
			margin-top: 27px;
		}
		.pricing-modals {
			display: flex;
			flex-direction: column;
			row-gap: 65px;
			margin-top: 79px;
		}
	}
	.footer-section {
		display: flex;
		flex-direction: column;
		row-gap: 31px;
		padding-top: 5px;
	}
	.footer-buttons {
		display: flex;
		flex-direction: column;
		justify-content: center;
		width: 100%;
		row-gap: 24px;
	}
	.footer-title {
		font-family: Manrope;
		font-size: 24px;
		font-weight: 800;
		line-height: 33px;
		letter-spacing: 1px;
		margin: 0 42px;
		text-align: center;
		color: $white;
	}
}

@media only screen and (min-width: 600px) {
	.navbar {
		justify-content: flex-start;
		margin-top: 48px;
		margin-left: 39px;
	}
	.main-header {
		background-image: url("./assets/LeftBG.svg"), url("./assets/PathBG.svg"),
			url("./assets/RightBG.svg");
		background-position: -35% 0, 50% 25px, 121% 0;
		background-size: 303px, 386px, 241px;
		margin-top: 77px;
		height: 343px;
		.sub-header {
			margin-top: 27px;
			width: 62%;
			.sub-title {
				padding-top: 25px;
			}
			.sub-description {
				padding: 0 0;
				margin-top: 24px;
			}
		}
	}
	.main-container {
		max-width: 100%;
		margin-top: 109px;
		margin-bottom: 105px;
		padding: 0 97px;
		row-gap: 119px;
	}

	.pricing-section {
		margin-top: 22px;
		.pricing-modals {
			padding: 0 64px;
		}
	}
	.footer-section {
		display: flex;
		flex-direction: column;
		width: 100%;
		row-gap: 24px;
		.footer-title {
			font-family: Manrope;
			font-size: 24px;
			font-weight: 800;
			line-height: 33px;
			letter-spacing: 0px;
			text-align: center;
			color: $white;
		}
		.footer-buttons {
			flex-direction: row;
			column-gap: 16px;
		}
		.footer-input-size {
			width: 320px;
		}
		.footer-button-size {
			width: 140px;
		}
	}
}
@media only screen and (min-width: 992px) {
	.navbar {
		justify-content: flex-start;
		margin-top: 81px;
		margin-left: 165px;
	}
	.main-header {
		background-image: url("./assets/LeftBG.svg"), url("./assets/PathBG.svg"),
			url("./assets/RightBG.svg");
		background-position: -5.5% 0, 50% 0px, 100% 0;
		background-size: 407px, 400px, 340px;
		margin-top: 114px;
		height: 459px;
		.sub-header {
			margin-top: 48px;
			width: 38%;
			.sub-title {
				font-size: 48px;
				line-height: 56px;
				padding: 25px 0px 0px;
				.colored-span {
					font-size: 48px;
					line-height: 56px;
					text-align: center;
					word-spacing: 1px;
					color: $light-blue;
				}
			}
			.sub-description {
				padding: 0 0;
				margin-bottom: 64px;
			}
		}
	}
	.main-container {
		max-width: 100%;
		padding: 0 165px;
		row-gap: 151px;
		margin-top: 202px;
		margin-bottom: 117px;
		.icons-section {
			display: flex;
			flex-direction: row;
			row-gap: 0;
			column-gap: 30px;
			width: inherit;
		}
		.pricing-section {
			margin-top: 51px;
			.pricing-title {
				font-size: 32px;
				line-height: 44px;
			}
			.pricing-description {
				margin: 24px 258px 105px;
			}
			.pricing-modals {
				flex-direction: row;
				align-items: center;
				padding: 0 65px;
				margin: 0 20px;
				width: 920px;
				column-gap: 30px;
			}
		}
		.footer-section {
			display: flex;
			flex-direction: column;
			width: 100%;
			row-gap: 24px;
			.footer-title {
				font-family: Manrope;
				font-size: 32px;
				font-weight: 800;
				line-height: 44px;
				word-spacing: 1px;
				text-align: center;
				color: $white;
			}
			.footer-buttons {
				flex-direction: row;
				column-gap: 16px;
			}
			.footer-input-size {
				width: 320px;
			}
			.footer-button-size {
				width: 140px;
			}
		}
	}
}
</style>
