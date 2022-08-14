<template>
	<nav class="navbar">
		<MakerIcon />
	</nav>
	<header class="main-header">
		<div class="sub-header">
			<h1 class="sub-title">Get paid for the work you love to do.</h1>
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
				<TextField class="footer-input-size" />
				<MButton class="footer-button-size" text="Get Notified" />
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
import LeftHalfBackground from "./components/svg/LeftHalfBackground.vue";
import RightHalfBackground from "./components/svg/RightHalfBackground.vue";
import PathSvg from "./components/svg/PathSvg.vue";
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
</script>

<style lang="scss">
@import "./assets/variables";

.navbar {
	display: flex;
	justify-content: center;
	margin-top: 40px;
}
.main-container {
	margin-top: 15px;
	display: flex;
	flex-direction: column;
	justify-content: center;
	padding-left: 24px;
	padding-right: 24px;
	align-items: center;
	row-gap: 15px;
	margin-top: 144px;
	margin-bottom: 164px;
}
.main-header {
	background-image: url("./assets/FullBG.svg");
	background-repeat: no-repeat;
	background-size: contain;
	margin-top: 66px;
	display: flex;
	justify-content: center;
	padding-left: 24px;
	padding-right: 24px;
}
.sub-header {
	display: flex;
	flex-direction: column;
	margin-top: 298px;
	align-items: center;
	width: 100%;

	.sub-title {
		font-style: normal;
		font-weight: 800;
		font-size: 32px;
		line-height: 40px;
		text-align: center;
		word-spacing: 1px;
		padding-left: 30px;
		padding-right: 30px;
		color: $white;
		z-index: 0;
		margin-block-start: 0em;
		margin-block-end: 0em;
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
		margin-top: 23px;
		margin-bottom: 32px;
	}
}

.icons-section {
	display: flex;
	flex-direction: column;
	row-gap: 56px;
	width: inherit;
}
.pricing-section {
	margin-bottom: 144px;
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
	}
	.pricing-modals {
		display: flex;
		flex-direction: column;
		row-gap: 65px;
		margin-top: 56px;
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
.path-svg {
	display: none;
}

@media only screen and (min-width: 600px) {
	.navbar {
		display: flex;
		justify-content: flex-start;
		margin-top: 48px;
		margin-left: 39px;
	}
	.main-container {
		display: flex;
		flex-direction: column;
		justify-content: center;
		max-width: 100%;
		padding-left: 97px;
		padding-right: 97px;
		align-items: center;
		row-gap: 15px;
	}
	/* chequear aca que esta pasando */
	.main-header {
		background-image: url("./assets/LeftBG.svg"), url("./assets/RightBG.svg");
		background-position: -36% 0, 121% 0;
		background-size: 303px, 241px;
		background-repeat: no-repeat;
		margin-top: 78px;
		display: flex;
		padding-left: 24px;
		padding-right: 24px;
	}

	.sub-header {
		background-image: url("./assets/PathBG.svg");
		background-position: 42% 9%;
		background-size: 461px 276px;
		background-repeat: no-repeat;
		margin-top: 27px;
		display: flex;
		flex-direction: column;
		width: 62%;
		height: 314px;
		align-items: center;

		.sub-title {
			font-style: normal;
			font-weight: 800;
			font-size: 32px;
			line-height: 40px;
			text-align: center;
			word-spacing: 1px;
			padding-top: 25px;
			padding-left: 30px;
			padding-right: 30px;
			color: $white;
			z-index: 0;
			margin-block-start: 0em;
			margin-block-end: 0em;
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
			margin-top: 23px;
			margin-bottom: 32px;
		}
	}

	.icons-section {
		display: flex;
		flex-direction: column;
		row-gap: 56px;
		width: inherit;
		margin-bottom: 141px;
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
		}
		.pricing-modals {
			display: flex;
			flex-direction: column;
			row-gap: 65px;
			margin-top: 56px;
			padding: 0 57px;
		}
	}
	.footer-section {
		display: flex;
		flex-direction: column;
		width: 100%;
		row-gap: 24px;
	}
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

	.path-svg {
		position: relative;
		display: block;
		top: -170px;
		z-index: -1;
	}
}
</style>
