<template>
	<view class="content">
		<searchBar></searchBar>
		<image class="logo" src="/static/logo.png"></image>
		<view class="text-area">
			<text class="title">{{title}}</text>
		</view>
		<text>不会全局社会化</text>
		<button type="warn" @click="handlePopup">警告按钮</button>
		<uni-popup ref="popup" type="top">底部弹出111 Popup</uni-popup>
	</view>
</template>

<script>
	// 单页面引入
	// import {uniPopup} from '@dcloudio/uni-ui';
	export default {
		data() {
			return {
				title: '小臂'
			}
		},
		components: {
			// uniPopup
		},
		onLoad() {

		},
		methods: {
			handlePopup() {
				if (this.$refs.popup) {
					this.$refs.popup.open();
				}
				console.log("hhh");
			}
		}
	}
</script>

<style>
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}

	.logo {
		height: 200rpx;
		width: 200rpx;
		margin-top: 200rpx;
		margin-left: auto;
		margin-right: auto;
		margin-bottom: 50rpx;
	}

	.text-area {
		display: flex;
		justify-content: center;
	}

	.title {
		font-size: 36rpx;
		color: #8f8f94;
	}
</style>
