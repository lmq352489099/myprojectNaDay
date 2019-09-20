<template>
	<view>
		<view class="row p-2  a-center j-sb border-bottom" v-for="(item,index) in gift" :key="index">
			<view>
				<image mode="widthFix" style="width:45px;height:45px" src="https://flycoinex.s3.ap-northeast-2.amazonaws.com/logo/1567740446344_8494287b7db94c99afbe003190244357.png"></image>
			</view>
			<view>{{item.experienceOfGold}}</view>
			<view>{{item.diamond}}
			</view>
			<view style="width: 40%;" class="a-center j-end d-flex">
							<view class="text-center text-white bg-exchangebgcolor rounded-2  line-h-lg" style="width: 200upx;">兑换</view>
			</view>

		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				gift: [{
					experienceOfGold: '1000体验金',
					diamond: '8钻',
				}]
			};
		},
		onLoad() {
			for (var i = 0; i < 20; i++) {
				this.gift.push({
					experienceOfGold: '1000体验金',
					diamond: '8钻',
				})
			}
		},
		onNavigationBarButtonTap() {
			// 
		}
	}
</script>

<style lang="scss">
</style>
