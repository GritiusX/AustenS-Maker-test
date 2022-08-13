<template>
	<div class="icon-box-container">
		<header class="icon">
			<EggSvg v-if="icon === 'egg'" :width="width" :height="height" />
			<MoneyjarSvg v-if="icon === 'moneyjar'" :width="width" :height="height" />
			<CocktailSvg v-if="icon === 'cocktail'" :width="width" :height="height" />
			<RoadtripSvg v-if="icon === 'roadtrip'" :width="width" :height="height" />
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
	width: {
		type: String,
		required: true,
	},
	height: {
		type: String,
		required: true,
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
	flex-direction: column;
	background-color: $blue;
	height: 124px;
	width: 120px;
	border-radius: 45px;
}
.footer {
	display: flex;
	flex-direction: column;
	text-align: center;
	width: inherit;
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
</style>
