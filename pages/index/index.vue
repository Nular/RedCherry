<template>
	
	<view class="content">
		<!-- <image class="logo" src="/static/logo.png"></image> -->
		<view class="top">
			<text class="step">
				{{step}}步
			</text>
		</view>
		<view class="center">
			
		</view>
		<view class="bottom">
			
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: 'Hello',
				step: 2333
			}
		},
		onLoad() {

		},
		methods: {

		}
	}
</script>

<style>  
	@import './index.css'; /*引入公共样式*/ 

</style>