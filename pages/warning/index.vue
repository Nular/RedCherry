<template>
	<view class="content">
	<view v-for="warning in warnings" class="entry">
		<view class="top">
			<view class="head">
				<image :src="warning.head" mode="aspectFill" />
			</view>
			<view class="user">{{ warning.user }}</view>
			<view class="time">{{ warning.time }}</view>
		</view>
		
		<view class="bottom">
			<view class="tip"><strong>{{ warning.tip }}</strong></view>
			<view class="message">{{ warning.message }}</view>
		</view>
	</view>
	</view>
</template>

<script>
	
	// message传值 例:
	var warning = {
		tip:"体温预警",
		message: "您体温19°C，体温偏低",
		user: "病者A",
		time: new Date().toLocaleTimeString(),
		head: "https://ss1.bdstatic.com/70cFvXSh_Q1YnxGkpoWK1HF6hhy/it/u=3836099653,977060296&fm=26&gp=0.jpg"
	}
	export default {
		data() {
			return {
				step: 2333,
				warnings: [ warning , warning , warning , warning ]
			}
		},
		onLoad() {

		},
		methods: {

		}
	}
</script>

<style>  
	.content {
		display: flex;
		flex-direction: column;
	}
	.entry{
		display: flex;
		flex-direction: column;
		
		width: 100%;
		height: 200rpx;
	}
	.entry>.top{
		display: flex;
		align-items: center;
		/* height: calc(50% - 20rpx); */
		height: 50%;
		width: 100%;
	}
	.entry>.top>.head{
		height: 100rpx;
		width: 100rpx;
	}
	.entry>.top>.head>image{
		height: 100rpx;
		width: 100rpx;
	}
	.entry>.top>.user{
		width: calc(100% - 100rpx - 180rpx);
		font-size: 36rpx;
		color: #007AFF;
	}
	.entry>.top>.time{
		height: 120rpx;
		width: 180rpx;
		
		font-size: 24rpx;
		color: #333333;
		
		display: flex;
		align-items: center;
	}
	.entry>.bottom{
		display: flex;
		height: calc(50% - 10rpx);
		width: 100%;
		padding-left: 18rpx;
		font-size: 24rpx;
	}
	.entry>.bottom>.tip{
		color: #DD524D;
	}
	.entry>.bottom>.message{
		padding-left: 36rpx;
	}
	
</style>