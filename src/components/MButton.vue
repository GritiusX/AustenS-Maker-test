<template>
	<span class="btn">{{ text }}</span>
</template>

<script setup>
defineProps({
	text: {
		type: String,
		default: "Button",
	},
});
</script>
<style lang="scss" scoped>
@import "../assets/variables";
.btn {
	display: flex;
	align-items: center;
	justify-content: center;
	width: inherit;
	height: 48px;
	background-color: $light-blue;
	border-radius: 24px;
	color: $blue;
	font-weight: 800;
	cursor: pointer;
}
.btn:hover {
	background-color: transparent;
	color: $white;
	outline: 2px solid $light-blue;
}
.btn:active {
	background-color: transparent;
	color: $white;
	outline: 2px solid $light-blue;
}
</style>
