<template>
	<view class="content bg-secondary ">
		<view class="uni-padding-wrap uni-common-mt">
			<view class="uni-title uni-common-mt">
				Vertical Scroll
				<text>\n纵向滚动</text>
			</view>
			<view>
				<scroll-view :scroll-top="scrollTop" scroll-y="true" class="scroll-Y" @scrolltoupper="upper" @scrolltolower="lower"
				 @scroll="scroll">
					<view id="demo1" class="scroll-view-item uni-bg-red">A</view>
					<view id="demo2" class="scroll-view-item uni-bg-green">B</view>
					<view id="demo3" class="scroll-view-item uni-bg-blue">C</view>
				</scroll-view>
			</view>
			<view @tap="goTop" class="uni-link uni-center uni-common-mt">
				点击这里返回顶部
			</view>
			<view class="uni-title uni-common-mt">
				Horizontal Scroll
				<text>\n横向滚动</text>
			</view>
			<view>
				<scroll-view class="scroll-view_H" scroll-x="true" @scroll="scroll" scroll-left="120">
					<view id="demo1" class="scroll-view-item_H uni-bg-red">A</view>
					<view id="demo2" class="scroll-view-item_H uni-bg-green">B</view>
					<view id="demo3" class="scroll-view-item_H uni-bg-blue">C</view>
				</scroll-view>
			</view>
		</view>
		<view class="px-2 flex-1">

			<!-- 中间图片部分 -->
			<view class="px-2 mb-4">

				<view class="bg-danger" style="width: 660upx;height: 510upx;"></view>
			</view>

			<!-- 我的钻石 -->
			<view class="w-100 d-flex flex-column a-center j-center rounded-tr" style="height: 180rpx;background-color: #F2F2F2;">
				<text class="font-md">我的钻石</text>
				<text class="font-lg text-primary">88</text>
			</view>
			<!-- tabbar 页面 -->
			<!-- 横向滚动导航 -->
			<view>
				<!-- 			<scroll-view
				 id="tab-bar"
				 class="uni-swiper-tab"
				 scroll-x
				 :scroll-left="scrollLeft">
					<view
					 v-for="(tab, index) in tabBars"
					 :key="tab.id"
					 class="swiper-tab-list"
					 :class="tabIndex == index ? 'active' : ''"
					 :id="tab.id"
					 :data-current="index"
					 @click="tapTab(index)">
						<view class="tabitems"> {{ tab.name }} </view>
					</view>
				</scroll-view> -->
				<scroll-view scroll-x="true">
					<view
					 v-for="(tab, index) in tabBars"
					 :key="tab.id"
					 class="swiper-tab-list"
					 :class="tabIndex == index ? 'active' : ''"
					 :id="tab.id"
					 :data-current="index"
					 @click="tapTab(index)">
						<view class="tabitems"> {{ tab.name }} </view>
					</view>
				</scroll-view>


			</view>
			<!-- 签到页面 -->
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				scrollTop: 0,
				old: {
					scrollTop: 0
				},
				scrollLeft: 0,
				title: 'Hello',
				tabIndex: 0,
				tabBars: [{
					name: '关注',
					id: 'guanzhu',
					template: "index"
				}, {
					name: '推荐',
					id: 'tuijian',
					template: "special"
				}, {
					name: '体育',
					id: 'tiyu',
					template: "special"
				}, {
					name: '热点',
					id: 'redian',
					template: "special"
				}, {
					name: '财经',
					id: 'caijing',
					template: "special"
				}, {
					name: '娱乐',
					id: 'yule',
					template: "special"
				}, {
					name: '军事',
					id: 'junshi',
					template: "special"
				}, {
					name: '历史',
					id: 'lishi',
					template: "special"
				}, {
					name: '本地',
					id: 'bendi',
					template: "special"
				}]
			}
		},
		onLoad() {

		},
		onReady() {
			// plus.navigator.setStatusBarBackground("#FF6666");

		},
		methods: {
			handle() {
				uni.navigateTo({
					url: "../cashGift/cashGift"
				})
			},
			tapTab(e) {
				console.log(e);
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
				this.scrollTop = this.old.scrollTop
				this.$nextTick(function() {
					this.scrollTop = 0
				});
				uni.showToast({
					icon: "none",
					title: "纵向滚动 scrollTop 值已被修改为 0"
				})
			}
		}
	}
</script>

<style>
	.status_bar {
		height: var(--status-bar-height);
		width: 100%;
		background: red;
	}

	.content {
		/* margin-top: 1210px; */
		/* height: 100%; */
		/* 	display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center; */

	}

	.logo {
		height: 200upx;
		width: 200upx;
		margin-top: 200upx;
		margin-left: auto;
		margin-right: auto;
		margin-bottom: 50upx;
	}

	.text-area {
		display: flex;
		justify-content: center;
	}

	.title {
		font-size: 36upx;
		color: #8f8f94;
	}

	.active .tabitems {
		border-bottom-color: #fd6801;
	}
</style>
