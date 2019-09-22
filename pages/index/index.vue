<template>
	<view>
		<view class="bg-image">
			<view class="bg__rule position-absolute right-0" style="top: 629rpx;">
				<image style="width: 175rpx;height: 70rpx;" src="../../static/集钻H5_slices/活动规则@2x.png" mode="widthFix"></image>
			</view>


		</view>

		<view class="main position-relative" style="margin-top: -364rpx;">
			<view class="bg-zuanshi d-flex  flex-column a-center">
				<view style="width: 700rpx;" class=" d-flex  flex-column a-center position-relative">
					<image style="width: 700rpx;height: 240rpx;" src="../../static/集钻H5_slices/我的钻石底部卡片（合并）@2x.png" mode=""></image>
					<image style="width: 680rpx;height: 140rpx;margin-top: -166rpx;" class="position-relative" src="../../static/集钻H5_slices/我的钻石外层部卡片（合并）@2x.png"
					 mode=""></image>


					<image class="guandao-first-image" style="height: 100rpx;width: 6rpx;  " src="../../static/集钻H5_slices/衔接管@2x.png"
					 mode="widthFix"></image>
					<image class="guandao-first-image_1" style="height: 100rpx;width: 6rpx;  " src="../../static/集钻H5_slices/衔接管@2x.png"
					 mode="widthFix"></image>
				</view>
			</view>

			<!-- g管道 -->
			<!-- 		<view class="position-absolute">
				<image class="guandao-first-image" style="height: 100rpx;width: 6rpx;  margin-left: 137rpx;  margin-top: -14rpx;"
				 src="../../static/集钻H5_slices/衔接管@2x.png" mode="widthFix"></image>

				<image class="guandao-first-image" style="height: 100rpx;width: 6rpx;  margin-left:468rpx;  margin-top: -14rpx;"
				 src="../../static/集钻H5_slices/衔接管@2x.png" mode="widthFix"></image>

			</view> -->



			<view class="bg-riqi d-flex  flex-column a-center" style="margin-top: 40rpx;background-color: rgb(254,219,193);">

				<view class="date d-flex a-center j-center position-relative">
					<view class="d-flex a-center j-center" style="width: 100%;">
						<text @click="hande" class="span-1 text-center"> 1</text>
						<view class="span-16" style="overflow: hidden;">
							<scroll-view class="scroll-view_H" scroll-x="true" @scroll="scroll">
									<view class="scroll-view-item_H ">10月1日</view>
					<view class="scroll-view-item_H ">10月1日</view>
					<view class="scroll-view-item_H ">10月2日</view>
					<view class="scroll-view-item_H ">10月3日</view>
					<view class="scroll-view-item_H ">10月4日</view>
					<view class="scroll-view-item_H ">10月5日</view>
					<view class="scroll-view-item_H ">10月7日</view>
							</scroll-view>
						</view>

						<text class="span-1 te">1 </text>
					</view>

					<image class="guandao-first-image" style="height: 100rpx;width: 6rpx;  " src="../../static/集钻H5_slices/衔接管@2x.png"
					 mode="widthFix"></image>
					<image class="guandao-first-image_1" style="height: 100rpx;width: 6rpx;  " src="../../static/集钻H5_slices/衔接管@2x.png"
					 mode="widthFix"></image>
				</view>
			</view>

			<!-- 列表 -->
			<view class="bg-list d-flex j-center" style="padding-top: 32rpx;background-color: rgb(254,219,193);">

				<view class="bg-image-list"></view>
			</view>

		</view>

      <scroll-view class="scroll-view_H" scroll-x="true" @scroll="scroll" scroll-left="120">
          <view id="demo1" class="scroll-view-item_H uni-bg-red">A</view>
          <view id="demo2" class="scroll-view-item_H uni-bg-green">B</view>
          <view id="demo3" class="scroll-view-item_H uni-bg-blue">C</view>
        </scroll-view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				scrollTop: 0,
				old: {
					scrollTop: 0
				}
			}
		},
		methods: {
			hande() {
				uni.navigateTo({
					url: '../ceshi/ceshi'
				})
			},
			upper: function(e) {
				console.log(e)
			},
			lower: function(e) {
				console.log(e)
			},
			scroll: function(e) {
				console.log(e)
				this.old.scrollTop = e.detail.scrollTop
			},
			goTop: function(e) {
				// 解决view层不同步的问题
				this.scrollTop = this.old.scrollTop
				this.$nextTick(function() {
					this.scrollTop = 0
				});
				uni.showToast({
					icon: "none",
					title: "纵向滚动 scrollTop 值已被修改为 0"
				})
			}
		},
	}
</script>

<style lang="scss" scoped>
	.bg-image {
		background: url(../../static/集钻H5_slices/头部背景@2x.png);
		background-size: cover;
		width: 100%;
		height: 100%;
		height: 1070rpx;
	}

	.guandao-first-image {
		height: 80rpx !important;
		position: absolute;
		left: 110rpx;
		bottom: -66rpx;
		z-index: 200;


	}

	.guandao-first-image_1 {
		height: 80rpx !important;
		position: absolute;
		right: 110rpx;
		bottom: -66rpx;
		z-index: 200;


	}

	.bg-riqi {
		.date {
			background: url(../../static/集钻H5_slices/日期卡片（合并）@2x.png);
			background-size: cover;
			width: 700rpx;
			height: 120rpx;

		}

	}

	.bg-image-list {

		background: url(../../static/集钻H5_slices/列表卡片（合并）@2x.png);
		background-repeat: no-repeat;
		background-size: contain;
		width: 700rpx;
		height: 1842rpx;
	}
	
	// .scroll-Y {
	// 	height: 300upx;
	// }
	// 
	.scroll-view_H {
		white-space: nowrap;
		width: 100%;
	}
	// 
	.scroll-view-item {
		height: 300upx;
		line-height: 300upx;
		text-align: center;
		font-size: 36upx;
	}
	// 
	.scroll-view-item_H {
		display: inline-block;
		width: 25%;
		// height: 300upx;
		// line-height: 300upx;
		text-align: center;
		font-size: 36upx;
		// height:25px;
font-size:28rpx;
font-family:PingFang SC;
font-weight:400;
color:rgba(130,58,22,1);
line-height:54rpx;
	}
</style>
