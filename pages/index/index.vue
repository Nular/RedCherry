<template>
	<scroll-view class="scroll-view" scroll-y="true" :scroll-top="scrollTop" @scroll="scroll" @scrolltoupper="upper"
	               @scrolltolower="lower">
	<view class="content">
		<!-- <image class="logo" src="/static/logo.png"></image> -->
		  
		<view class="toplist">
			<!-- 红色圆1.0
			<canvas style="width: 100px; height: 100px;" canvas-id="firstCanvas"></canvas> -->
		   <!-- 红色笑脸
			<canvas style="width: 300px; height: 200px;" canvas-id="firstCanvas"></canvas> -->
				<!-- <text class="step">
					{{step}}步
				</text> -->
			<canvas class="canvas" :canvas-id="canvas"></canvas>
		</view>
		<view class="center">
			<view class="top">
				<text class="gps">位置信息</text>
			</view>
			<!-- 心率、血压、体温、睡眠大框 -->
			<view class="bottom">
				<view class="firstbox">
					<view class="hr">
						<image src="/static/images/hr.png" mode=""></image>
						
						<text class="alldata">{{hrdata}}</text>
						<text class="allstatus">{{hrstatus}}</text>
						<text>心率记录</text>
						
					</view>
					<view class="bp">
						<image src="/static/images/hr.png" mode=""></image>
						
						<text class="alldata">{{bpdata}}</text>
						<text class="allstatus">{{bpstatus}}</text>
						<text>血压记录</text>
					</view>
				</view>
				<view class="secondbox">
					<view class="tp">
						<image src="/static/images/hr.png" mode=""></image>	
						<text class="alldata">{{tpdata}}</text>
						<text class="allstatus">{{tpstatus}}</text>
						<text>体温记录</text>
					</view>
					<view class="sp">
						<image src="/static/images/hr.png" mode=""></image>
						
						<text class="alldata">{{spdata}}</text>
						<text class="allstatus">{{spstatus}}</text>
						<text>睡眠记录</text>
					</view>
				</view>
			</view>
			
		</view>
	</view>
	</scroll-view>
</template>

<script>
	// import {cavas} from '../../canvas.js'
	export default {
		data() {
			return {
				title: 'Hello',
				step: 2333,
				hrdata:84+"次/分",
				hrstatus:"非常健康",
				bpdata:126.0+"/"+78.0+"mmHg",
				bpstatus:"非常健康",
				tpdata: 36.8+"°C",
				tpstatus:"非常健康",
				spdata:"深睡:0,浅睡:0",
				spstatus:"暂无数据",
				scrollTop:0,
				old:{
					scrollTop:0
				},
				canvas: "step",
			}
		},
		onReady: function (e) {
			//绿色框加红色笑脸
			//    var context = uni.createCanvasContext('firstCanvas')
			//         context.setStrokeStyle("#00ff00")
			//         context.setLineWidth(5)
			//         context.rect(0, 0, 200, 200)
			//         context.stroke()
			//         context.setStrokeStyle("#ff0000")
			//         context.setLineWidth(2)
			//         context.moveTo(160, 100)
			//         context.arc(100, 100, 60, 0, 2 * Math.PI, true)
			//         context.moveTo(140, 100)
			//         context.arc(100, 100, 40, 0, Math.PI, false)
			//         context.moveTo(85, 80)
			//         context.arc(80, 80, 5, 0, 2 * Math.PI, true)
			//         context.moveTo(125, 80)
			//         context.arc(120, 80, 5, 0, 2 * Math.PI, true)
			//         context.stroke()
			//         context.draw()
			
			//红圆1.0
			 // var context = uni.createCanvasContext('firstCanvas')
		  //       context.setStrokeStyle("#ff0000")
		  //       context.setLineWidth(2)
		  //       context.arc(40, 50, 30, 0, 2 * Math.PI, true)
				// context.font = '10px Arial';
				// context.fillStyle = '#f30';
				// context.textBaseline = 'middle';
				// context.textAlign = 'center';
				// context.fillText('233步', 40,50);
				// context.stroke()
				// context.draw()
			},
		onLoad: function () {
			this.drawStep(this.canvas)
		},
		
		methods: {
			drawStep(canvas) {
				var turn = 0;
				setInterval(() => {
					if(turn > 2000){
						turn = 0;
					}
					else{
						turn += 10;
					}
					const ctx = uni.createCanvasContext(canvas); //拿到canvas对象（自己的定义的canvas-id）
					// 开始绘制第一条路径 总数 红色
					ctx.beginPath(); // 开始绘制路径
					ctx.arc(145,60, 45, 0, 2 * Math.PI); // arc画圆
					ctx.setStrokeStyle("#ffffff"); // 线条颜色
					ctx.setLineWidth(5); // 线条宽度
					ctx.stroke(); // 绘制成线条（fill()是填充为饼图）
					// 开始绘制第二条路径
					ctx.beginPath();
					ctx.arc(145, 60, 45, turn / 1000 * Math.PI, 1.5 * Math.PI - turn / 1000 * Math.PI);
					ctx.setStrokeStyle("#98f2ff");
					ctx.setLineWidth(5);
					ctx.stroke();
					// 填充字体-367
					ctx.setFillStyle("#ffffff");
					ctx.setFontSize(18);
					ctx.setTextAlign("center");
					ctx.fillText(this.step + "步", 145, 70);
					ctx.stroke();
					// 渲染
					ctx.draw();
				}, 100);
				
			},
			scroll(e) {
						this.old.scrollTop = e.detail.scrollTop
			},
			goTop() {
				//这里必须将this.old.scrollTop值赋值给this.scrollTop
				this.scrollTop = this.old.scrollTop;
				this.$nextTick(function() {
					this.scrollTop = 0
				});
			},
			upper(){
				// 滚动到顶部/左边触发
			},
			lower(){
				// 滚动到底部/右边触发
			}
				        
		},
		
		
	}
</script>

<style>  
	@import './index.css'; /*引入公共样式*/ 

</style>