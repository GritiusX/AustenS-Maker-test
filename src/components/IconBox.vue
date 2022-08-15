<template>
	<div class="icon-box-container">
		<header class="icon">
			<EggSvg v-if="icon === 'egg'" class="egg" />
			<MoneyjarSvg v-if="icon === 'moneyjar'" class="moneyjar" />
			<CocktailSvg v-if="icon === 'cocktail'" class="cocktail" />
			<RoadtripSvg v-if="icon === 'roadtrip'" class="roadtrip" />
		</header>
		<footer class="footer">
			<h3>{{ title }}</h3>
			<p>{{ description }}</p>
		</footer>
	</div>
</template>
<script setup>
import EggSvg from "../components/svg/EggSvg.vue";
import MoneyjarSvg from "../components/svg/MoneyjarSvg.vue";
import CocktailSvg from "../components/svg/CocktailSvg.vue";
import RoadtripSvg from "../components/svg/RoadtripSvg.vue";

defineProps({
	icon: {
		type: String,
		default: "egg",
	},
	title: {
		type: String,
		default: "title",
	},
	description: {
		type: String,
		default: "description",
	},
});
</script>
<style lang="scss" scoped>
@import "../assets/variables";
.icon-box-container {
	width: 327px;
	display: flex;
	flex-direction: column;
	align-items: center;
	justify-content: center;
}
.icon {
	display: flex;
	align-items: center;
	justify-content: center;
	background-color: $blue;
	height: 124px;
	width: 120px;
	border-radius: 45px;
}
.egg {
	width: 66px;
	height: 88px;
}
.moneyjar {
	width: 56px;
	height: 67px;
}
.cocktail {
	width: 60px;
	height: 71px;
}
.roadtrip {
	width: 78px;
	height: 56px;
}
.footer {
	display: flex;
	flex-direction: column;
	text-align: center;
	margin-top: 32px;
	row-gap: 11px;
	word-spacing: 1px;
	h3 {
		color: $white;
		font-size: 18px;
		font-weight: 800;
		line-height: 25px;
		margin-block-start: 0em;
		margin-block-end: 0em;
	}
	p {
		font-size: 15px;
		font-weight: 500;
		line-height: 25px;
		color: $grey;
		margin-block-start: 0em;
		margin-block-end: 0em;
	}
}
@media only screen and (min-width: 600px) {
	.icon-box-container {
		width: 515px;
		flex-direction: row;
	}
	.icon-box-container:nth-child(odd) {
		margin-left: 58px;
	}
	.icon {
		display: flex;
		align-items: center;
		justify-content: center;
		flex-direction: column;
		background-color: $blue;
		height: 124px;
		width: 39%;
		border-radius: 45px;
	}

	.footer {
		text-align: start;
		margin-top: 0;
		margin-left: 55px;
		word-spacing: 0;
	}
}
@media only screen and (min-width: 992px) {
	.icon-box-container {
		width: 255px;
		height: 335px;
		flex-direction: column;
		align-items: flex-start;
		row-gap: 48px;
	}
	.icon-box-container:nth-child(odd) {
		margin-left: 0;
	}
	.icon-box-container:nth-child(even) {
		margin-top: 48px;
	}
	.icon {
		flex-direction: column;
		background-color: $blue;
		height: 164px;
		width: 160px;
		border-radius: 45px;
	}
	.egg {
		width: 88px;
		height: 106px;
	}
	.moneyjar {
		width: 74px;
		height: 89px;
	}
	.cocktail {
		width: 80px;
		height: 94px;
	}
	.roadtrip {
		height: 74px;
		width: 104px;
	}
	.footer {
		margin-left: 0px;
		row-gap: 23px;
		word-spacing: 0;
		h3 {
			color: $white;
			font-size: 18px;
			font-weight: 800;
			line-height: 25px;
			margin-block-start: 0em;
			margin-block-end: 0em;
		}
		p {
			font-size: 15px;
			font-weight: 500;
			line-height: 25px;
			color: $grey;
			margin-block-start: 0em;
			margin-block-end: 0em;
		}
	}
}
</style>
