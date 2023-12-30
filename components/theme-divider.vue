<template>
	<view class="" style="overflow: auto">
		<view class="theme-divider" :style="style"> </view>
	</view>
</template>

<script>
	export default {
		name: "theme-divider",
		props: {
			mt: {
				type: [String, Number],
				default: 0,
			},
			mb: {
				type: [String, Number],
				default: 1,
			},
			mx: {
				type: [String, Number],
				default: 0,
			},
			my: {
				type: [String, Number],
				default: 0,
			},
		},
		computed: {
			style() {
				const t = this.my;
				const r = this.mx;
				const b = this.mb || this.my;
				const l = this.mx;
				return {
					margin: `${t}px ${r}px ${b}px ${l}px`,
				};
			},
		},
	};
</script>

<style scoped>
	.theme-divider {
		position: relative;
	}

	.theme-divider::after {
		content: "";
		position: absolute;
		left: 0;
		top: 0;
		width: 200%;
		height: 200%;
		border-bottom: 1px solid #e6e6e6;
		-webkit-transform-origin: 0 0;
		transform-origin: 0 0;
		-webkit-transform: scale(0.5);
		transform: scale(0.5);
	}
</style>