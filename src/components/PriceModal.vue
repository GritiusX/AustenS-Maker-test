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
			<h3 class="title">
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
	position: relative;
	height: 100%;
	border-radius: 8px;
	font-weight: 500;
	&.free {
		background-color: $blue;
		color: $white;
		padding: 49px 30px 32px;
	}
	&.priced {
		background-color: $light-blue;
		color: $black;
		padding: 61px 30px 32px;
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
}
.description {
	font-family: Manrope;
	font-size: 15px;
	line-height: 25px;
	text-align: left;
	opacity: 0.6;
	margin-top: 19px;
	margin-bottom: 26px;
}
.price {
	font-family: Manrope;
	font-size: 40px;
	font-weight: 800;
	line-height: 55px;
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
		&.free {
			background-color: $blue;
			color: $white;
			padding: 49px 38px 48px;
		}
		&.priced {
			background-color: $light-blue;
			color: $blue;
			padding: 61px 38px 60px;
		}
	}
	.title {
		margin-top: 0;
		margin-block-start: 0em;
		margin-block-end: 0em;
	}
	.description {
		margin-bottom: 24px;
	}
	.price {
		margin-block-start: 0em;
		margin-block-end: 0em;
	}
	.check-li {
		p {
			margin-block-start: 0em;
			margin-block-end: 0em;
		}
	}
	.footer {
		margin-block-end: 0em;
	}
}
@media only screen and (min-width: 992px) {
	.price-modal-container {
		&.free {
			background-color: $blue;
			color: $white;
			padding: 49px 58px 48px;
		}
		&.priced {
			background-color: $light-blue;
			color: $blue;
			padding: 61px 38px 60px;
		}
	}
	.title {
		margin-top: 0;
		margin-block-start: 0em;
		margin-block-end: 0em;
	}
	.description {
		text-align: left;
	}
	.price {
		margin-block-start: 0em;
		margin-block-end: 0em;
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
