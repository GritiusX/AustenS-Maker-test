<template>
	<section
		:class="
			price == 'Free'
				? 'price-modal-container free'
				: 'price-modal-container priced'
		"
	>
		<IconsPriceModal
			:class="price == 'Free' ? 'svg-position free' : 'svg-position priced'"
			:price="price"
		/>
		<header>
			<h3 :class="price == 'Free' ? 'title free' : 'title priced'">
				{{ title }}
			</h3>
			<p class="description">{{ description }}</p>
		</header>
		<p v-if="price == 'Free'" class="price">{{ price }}</p>
		<p v-else class="price">
			${{ price }} <span class="month-span">/month</span>
		</p>
		<ul class="footer">
			<li v-for="check in checks" :key="check" class="check-li">
				<CheckIcon :price="price" />
				<p>{{ check }}</p>
			</li>
		</ul>
	</section>
</template>

<script setup>
import IconsPriceModal from "./svg/IconsPriceModal.vue";
import CheckIcon from "./svg/CheckIcon.vue";
defineProps({
	title: {
		type: String,
		default: "title",
	},
	description: {
		type: String,
		default: "description",
	},
	price: {
		type: String,
		default: "free",
	},
	checks: {
		type: Array,
		default: [],
	},
});
</script>

<style lang="scss" scoped>
@import "../assets/variables";
.price-modal-container {
	&.free {
		background-color: $blue;
		color: $white;
	}
	&.priced {
		background-color: $light-blue;
		color: $black;
	}
	position: relative;
	padding-left: 30px;
	padding-right: 30px;
	padding-top: 49px;
	padding-bottom: 32px;
	height: 100%;
	border-radius: 8px;
	font-weight: 500;
}
.svg-position {
	position: absolute;
	left: 30px;

	&.free {
		top: -20px;
	}
	&.priced {
		top: -33px;
	}
}
.title {
	font-family: Manrope;
	font-size: 18px;
	font-weight: 800;
	line-height: 25px;
	letter-spacing: 0px;
	text-align: left;
	margin-top: 12px;
}
.description {
	font-family: Manrope;
	font-size: 15px;
	line-height: 25px;
	letter-spacing: 0px;
	margin-top: 19px;
	margin-bottom: 26px;
	text-align: left;
	opacity: 0.6;
	word-spacing: 1px;
}
.price {
	font-family: Manrope;
	font-size: 40px;
	font-weight: 800;
	line-height: 55px;
	letter-spacing: 0px;
	text-align: left;
}
.month-span {
	font-family: "Manrope";
	font-style: normal;
	font-weight: 500;
	font-size: 15px;
	line-height: 25px;
}
.check-li {
	display: flex;
	align-items: center;
	column-gap: 16px;
	text-align: left;
	p {
		font-family: "Manrope";
		font-style: normal;
		font-weight: 500;
		font-size: 15px;
		line-height: 25px;
	}
}
.footer {
	display: flex;
	flex-direction: column;
	list-style: none;
	row-gap: 12px;
	margin-top: 19px;
	padding-inline-start: 0px;
}

@media only screen and (min-width: 600px) {
	.price-modal-container {
		position: relative;
		padding: 49px 38px 48px;
		height: 100%;
		border-radius: 8px;
		font-weight: 500;
		&.free {
			background-color: $blue;
			color: $white;
		}
		&.priced {
			background-color: $light-blue;
			color: $black;
		}
	}
	.svg-position {
		position: absolute;
		left: 30px;

		&.free {
			top: -20px;
		}
		&.priced {
			top: -33px;
		}
	}
	.title {
		font-family: Manrope;
		font-size: 18px;
		font-weight: 800;
		line-height: 25px;
		letter-spacing: 0px;
		text-align: left;
		margin-top: 0;
		margin-block-start: 0em;
		margin-block-end: 0em;
	}
	.description {
		font-family: Manrope;
		font-size: 15px;
		line-height: 25px;
		letter-spacing: 0px;
		margin-top: 19px;
		margin-bottom: 24px;
		text-align: left;
		opacity: 0.6;
		word-spacing: 1px;
	}
	.price {
		font-family: Manrope;
		font-size: 40px;
		font-weight: 800;
		line-height: 55px;
		letter-spacing: 0px;
		text-align: left;
		margin-block-start: 0em;
		margin-block-end: 0em;
	}
	.month-span {
		font-family: "Manrope";
		font-style: normal;
		font-weight: 500;
		font-size: 15px;
		line-height: 25px;
	}
	.check-li {
		display: flex;
		align-items: center;
		column-gap: 16px;
		text-align: left;
		p {
			font-family: "Manrope";
			font-style: normal;
			font-weight: 500;
			font-size: 15px;
			line-height: 25px;
			margin-block-start: 0em;
			margin-block-end: 0em;
		}
	}
	.footer {
		display: flex;
		flex-direction: column;
		list-style: none;
		row-gap: 12px;
		margin-top: 19px;
		padding-inline-start: 0px;
		margin-block-end: 0em;
	}
}
</style>
