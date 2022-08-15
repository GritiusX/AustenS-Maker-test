<template>
	<div class="text-field-container">
		<input
			:class="error ? 'text-field error' : 'text-field'"
			:value="modelValue"
			type="email"
			placeholder="Email address"
			@input="$emit('update:modelValue', $event.target.value)"
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
	modelValue: {
		type: String,
		default: "",
	},
	error: {
		type: Boolean,
		default: false,
	},
});
defineEmits(["update:modelValue"]);
</script>

<style lang="scss" scoped>
@import "../assets/variables";

.text-field-container {
	display: flex;
	flex-direction: column;
}
.text-field {
	box-sizing: border-box;
	height: 48px;
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
