<template>
	<view class="content">
	
	<view v-for="msg in messages" class="entry">
		<view class="head">
			<image :src="msg.head" mode="aspectFill" />
		</view>
		
		<view class="center">
			
			<view class="sender">{{msg.sender}}</view>
			<view class="content">{{msg.content}}</view>
			
		</view>
		
		<view class="time">{{ msg.time }}</view>
	</view>
		
	</view>
</template>

<script>
	
	// message传值 例:
	var massage = {
		content: "今天天气真好吖hhhhhhh",
		time: new Date().toLocaleTimeString(),
		sender: "天气问候者",
		head: "https://ss1.bdstatic.com/70cFvXSh_Q1YnxGkpoWK1HF6hhy/it/u=3836099653,977060296&fm=26&gp=0.jpg"
	}
	export default {
		data() {
			return {
				step: 2333,
				messages: [ massage , massage , massage , massage ]
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
	.content>.entry{
		display: flex;
		flex-direction: row;
		
		width: 100%;
		height: 120rpx;
		
	}
	.content>.entry>.head{
		height: 120rpx;
		width: 120rpx;
	}
	.content>.entry>.head>image{
		height: 120rpx;
		width: 120rpx;
	}
	.content>.entry>.center{
		height: 120rpx;
		width: calc(100% - 120rpx - 180rpx);
	}
	.content>.entry>.center>.sender{
		height: calc(50% - 20rpx);
		margin-top: 20rpx;
		font-size: 36rpx;
		color: #007AFF;
	}
	.content>.entry>.center>.content{
		height: calc(50% - 10rpx);
		font-size: 24rpx;
		margin-top: 10rpx;
	}
	.content>.entry>.time{
		height: 120rpx;
		width: 180rpx;
		
		font-size: 24rpx;
		color: #333333;
		
		display: flex;
		align-items: center;
	}
</style>