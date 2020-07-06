<template>
	<view class="content">
		<view class="user">
			<image class="head" :src="user.head" mode="aspectFill"></image>
			<view class="name"><strong>{{ user.name }}</strong></view>
			<view class="phone">{{ user.phone }}</view>
		</view>
		<view class="row">
			<view v-for="(element, index) in elements" v-if="index < 5" class="element">
				<image :src="element.icon" mode="aspectFit"></image>
				<view class="tip">{{ element.tip }}</view>
			</view>
		</view>
		<view class="row">
			<view v-for="(element, index) in elements" v-if="index >= 5" class="element">
				<image :src="element.icon" mode="aspectFit"></image>
				<view class="tip">{{ element.tip }}</view>
			</view>
		</view>
		<view class="logout">注销登录</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				user: {
					name: 'Nular',
					// head: 'https://ss1.bdstatic.com/70cFvXSh_Q1YnxGkpoWK1HF6hhy/it/u=3836099653,977060296&fm=26&gp=0.jpg',
					head: 'http://img1.imgtn.bdimg.com/it/u=1462833467,3467912640&fm=26&gp=0.jpg',
					phone: '17558406120',
				},
				elements:[
					{
						icon:'http://img3.imgtn.bdimg.com/it/u=3517898212,1906939989&fm=26&gp=0.jpg',
						nativeTo:'',
						tip:'我的二维码',
					},
					{
						icon:'http://img3.imgtn.bdimg.com/it/u=3517898212,1906939989&fm=26&gp=0.jpg',
						nativeTo:'',
						tip:'绑定设备',
					},
					{
						icon:'http://img3.imgtn.bdimg.com/it/u=3517898212,1906939989&fm=26&gp=0.jpg',
						nativeTo:'',
						tip:'绑定亲属',
					},
					{
						icon:'http://img3.imgtn.bdimg.com/it/u=3517898212,1906939989&fm=26&gp=0.jpg',
						nativeTo:'',
						tip:'关注请求',
					},
					{
						icon:'http://img3.imgtn.bdimg.com/it/u=3517898212,1906939989&fm=26&gp=0.jpg',
						nativeTo:'',
						tip:'签约医生',
					},
					{
						icon:'http://img3.imgtn.bdimg.com/it/u=3517898212,1906939989&fm=26&gp=0.jpg',
						nativeTo:'',
						tip:'签约护士',
					},
					{
						icon:'http://img3.imgtn.bdimg.com/it/u=3517898212,1906939989&fm=26&gp=0.jpg',
						nativeTo:'',
						tip:'电子围栏',
					},
					{
						icon:'http://img3.imgtn.bdimg.com/it/u=3517898212,1906939989&fm=26&gp=0.jpg',
						nativeTo:'',
						tip:'健康报告',
					},
					{
						icon:'http://img3.imgtn.bdimg.com/it/u=3517898212,1906939989&fm=26&gp=0.jpg',
						nativeTo:'',
						tip:'紧急呼叫',
					},
					{
						icon:'http://img3.imgtn.bdimg.com/it/u=3517898212,1906939989&fm=26&gp=0.jpg',
						nativeTo:'',
						tip:'修改密码',
					}
				]
			}
		},
		methods: {

		}
	}
</script>

<style>  
.user{
	display: flex;
	flex-direction: column;
	align-items: center;
	justify-content: space-around;
	padding-top: 100rpx;
}
.user>.head{
	width: 150rpx;
	height: 150rpx;
	border-radius:150rpx;
	border: 3px double #007AFF;
	/* border-style: double; */
}
.user>.name{
	align-items: center;
	font-size: 52rpx;
	color: #007AFF;
}
.user>.phone{
	align-items: center;
	font-size: 30rpx;
	color: #777777;
}
.row{
	display: flex;
	flex-direction: row;
	flex-wrap: wrap;
	justify-content: space-around;
	height: 150rpx;
	margin: 150rpx 0;
}
.row>.element{
	display: flex;
	height: 150rpx;
	width: calc(20% - 20rpx);
	flex-direction: column;
	align-items: center;
}
.row>.element>image{
	height: 100rpx;
	width: 100rpx;
}
.row>.element>.tip{
	font-size: 26rpx;
	color: #2C405A;
}
.logout{
	display: flex;
	justify-content: center;
	
	font-size: 48rpx;
	color: #FF3333;
}

</style>