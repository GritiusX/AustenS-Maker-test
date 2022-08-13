<template>
	<svg
		v-if="price === 'Free'"
		:width="width"
		:height="height"
		viewBox="0 0 12 9"
		fill="none"
		xmlns="http://www.w3.org/2000/svg"
	>
		<path
			d="M10.3186 0.768066L11.6813 2.23203L4.55387 8.8662L0.318604 4.92402L1.68126 3.46006L4.55293 6.13405L10.3186 0.768066Z"
			fill="#3EE9E5"
		/>
	</svg>
	<svg
		v-else
		:width="width"
		:height="height"
		viewBox="0 0 12 9"
		fill="none"
		xmlns="http://www.w3.org/2000/svg"
	>
		<path
			d="M10.3186 0.768066L11.6813 2.23203L4.55387 8.8662L0.318604 4.92402L1.68126 3.46006L4.55293 6.13405L10.3186 0.768066Z"
			fill="#093F68"
		/>
	</svg>
</template>
<script setup>
defineProps({
	width: { type: String, default: "12" },
	height: { type: String, default: "9" },
	price: { type: String, default: "Free" },
});
</script>
<style lang="scss" scoped></style>
