<template>
	<view class="psdIptBx">
		<block v-for="(item , index) in psdIptNum" :key='index'>
			<view class="psdTtem">
				<text v-if="numLng.length > index" class="psdTtemTxt">
					<text v-if="plaintext">●</text>
					<text v-else>{{numLng[index]}}</text>
				</text>
				<text v-if="isFocus && numLng.length == index" class="focus_move">|</text>
			</view>
		</block>
	</view>
</template>

<script>
	export default {
		props: {
			//是否明文 默认密文
			plaintext: {
				type: Boolean,
				default: true
			},
			//键盘输入的val
			numLng: {
				type: [String, Number],
				default: ''
			},
			//密码框的个数
			psdIptNum: {
				type: [String, Number],
				default: 6
			},
			isFocus: {
				type: Boolean,
				default: true
			}
		},
		data() {
			return {}
		},
		created() {},
		mounted() {},
		methods: {}
	}
</script>

<style scoped>
	.psdIptBx {
		display: flex;
		width: 100%;
		text-align: center;
		/* border-bottom: 1px solid #ccc; */
		/* border-top: 1px solid #ccc; */
		/* border-right: 1px solid #ccc; */
	}

	.psdTtem {
		flex: 1;
		width: 48px;
		height: 44px;

		border-radius: 7px;

		/* border-left: 1px solid #ccc; */
		line-height: 1;
		background-color: #F7F7F9;

		margin-right: 10px;

	}

	.psdTtemTxt {
		text-align: center;
		line-height: 80rpx;
		font-size: 30rpx;
	}

	.focus_move {
		color: #333;
		font-size: 30rpx;
		line-height: 80rpx;
		animation: focus 0.8s infinite;
	}

	@keyframes focus {
		from {
			opacity: 1;
		}

		to {
			opacity: 0;
		}
	}
</style>