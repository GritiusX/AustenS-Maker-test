<template>
	<div class="text-field-container">
		<input
			:class="error ? 'text-field error' : 'text-field'"
			type="email"
			placeholder="Email address"
		/>
		<label v-if="error" class="text-field-error">{{ text }}</label>
	</div>
</template>

<script setup>
defineProps({
	text: {
		type: String,
		default: "Oops! That doesn't look like an email address",
	},
	error: {
		type: Boolean,
		default: false,
	},
});
</script>

<style lang="scss" scoped>
@import "../assets/variables";

.text-field-container {
	display: flex;
	flex-direction: column;
}
.text-field {
	height: 48px;
	width: inherit;
	border-radius: 24px;
	border: 0px;
	background-color: $blue;
	color: $white;
	font-weight: 800;
	padding-left: 18px;
	&.error {
		outline: 2px $red solid;
	}
}
.text-field:focus-visible {
	outline: 2px $light-blue solid;
	&.error:focus-visible {
		outline: 2px $red solid;
	}
}
.text-field-error {
	color: $red;
	margin-left: 18px;
	font-size: 12px;
	line-height: 25px;
	font-weight: 500;
}
</style>
