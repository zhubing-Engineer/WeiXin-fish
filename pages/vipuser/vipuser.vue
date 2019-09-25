<template>
	<view class="content">
		<view class="backimg">
			<image class="bgimg-all" src="../../static/vip/vipbgimg1.png"></image>
			<image class="bgimg-box" src="../../static/vip/tuoyuan.png"></image>
			<view class="img-top">
				<view style="width: 78%;font-size: 34upx;display: flex;display: -webkit-flex;flex-wrap: nowrap;">
					<view style="">
						<image src="../../static/vip/kefutouxiang.png" style="width: 90upx;height: 90upx;border-radius: 50%;"></image>
					</view>
					<view style="display: flex;display: -webkit-flex;flex-direction: column;width: 70%;margin-left: 12upx;">
						<text style="margin-top: 6upx;">小川UU</text>
						<text style="font-size: 27upx;">您还不是VIP会员</text>
					</view>
				</view>
				<view style="width: 22%;font-size: 27upx;line-height: 100upx;">
					立即开通 >
				</view>
			</view>
			<view class="img-content">
				<view class="img-content-left">
					<view class="img-gdx">
						<image class="img-img" src="../../static/vip/shegbi.png" ></image>
						<text class="img-text">省币</text>
					</view>
					<view class="img-fpx"> 
						2222
					</view>
				</view>
				<view class="img-content-right">
					<view class="img-gdx" >
						<image class="img-img" src="../../static/vip/jingbi.png"></image>
						<text class="img-text" >金币</text>
					</view>
					<view class="img-fpx">
						2222
					</view>
				</view>
			</view>
			<view class="vip-text">会员八大特权</view>
			<view class="cate-section">
				<view class="cate-item">
					<image src="/static/vip/dikoujuan.png"></image>
					<text>300元卷</text>
				</view>
				<view class="cate-item">
					<image src="/static/vip/yueyouhui.png"></image>
					<text>月优惠券</text>
				</view>
				<view class="cate-item">
					<image src="/static/vip/shengrizhekou.png"></image>
					<text>生日优惠</text>
				</view>
				<view class="cate-item">
					<image src="/static/vip/mianfeishiyon.png"></image>
					<text>免费试用</text>
				</view>
				<view class="cate-item">
					<image src="/static/vip/shuangbeishengbi.png"></image>
					<text>双倍省币</text>
				</view>
				<view class="cate-item">
					<image src="/static/vip/quanchangzunxiang.png"></image>
					<text>全场专享</text>
				</view>
				<view class="cate-item">
					<image src="/static/vip/zxkefu.png"></image>
					<text>专属客服</text>
				</view>
				<view class="cate-item">
					<image src="/static/vip/shwngri.png"></image>
					<text>生日专享</text>
				</view>
			</view>
			<button class="btn-vip">
				立即成为VIP会员
			</button>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			}
		},
		onLoad(){
			
		},
		methods: {
			
		}
	}
</script>

<style lang='scss'>
	page,
	.content {
		height: 100%;
		background-color: #f8f8f8;
	}
	
	.content {
		display: flex;
	}
	.backimg{
		width: 100%;
	}
	.bgimg-all{
		position: relative;
		height: 850upx;
		width: 100%;
	}
	.bgimg-box{
		width: 90%;
		position: absolute;
		left: 5%;
		top: 0;
		height: 310upx;
	}
	.img-top{
		width: 85%;
		height: 100upx;
		position: absolute;
		left: 5%;
		top: 0;
		display: flex;
		display: -webkit-flex; /* Safari */ 
		margin: 20upx;
		color: white;
	}
	.img-content{
		width: 85%;
		position: absolute;
		height: 150upx;
		left: 5%;
		top: 110upx;
		background: rgba(251,251,251,0.1);
		margin: 20upx;
		display: flex;
		flex-wrap: nowrap;
	}
	.img-content-left{
		width: 50%;
		height: 100%;
		display: flex;
		display: -webkit-flex;
		flex-direction: column;
	}
	
	.img-content-right{
		width: 50%;
		height: 100%;
		display: flex;
		display: -webkit-flex;
		flex-direction: column;
	}
	.vip-text{
		font-size: 16px;
		color: #FCEEC2;
		position: absolute;
		top: 330upx;
		width: 100%;
		text-align: center;
	}
	.cate-section {
		position: absolute;
		top: 380upx;
		display: flex;
		justify-content: space-around;
		align-items: center;
		flex-wrap:wrap;
		padding: 30upx 22upx; 
		width: 100%;
		.cate-item {
			display: flex;
			flex-direction: column;
			align-items: center;
			font-size: $font-sm + 2upx;
			color:white;
			margin: 0 25upx 20upx 25upx;
		}
		/* 原图标颜色太深,不想改图了,所以加了透明度 */
		image {
			width: 88upx;
			height: 88upx;
			margin-bottom: 14upx;
			border-radius: 50%;
			box-shadow: 4upx 4upx 20upx rgba(250, 67, 106, 0.3);
		}
	}
	.btn-vip{
		width: 82%;
		height: 80upx;
		position: absolute;
		top: 730upx;
		background:linear-gradient(70deg,#FDEBBF 0%, #E9CA74 100%);
		left: 9%;
		border-radius: 55upx;
		color: black;
	}
	.img-gdx{
		text-align: center;
		height: 70upx;
		line-height: 70upx;
	}
	.img-img{
		width: 40upx;
		height: 40upx;
		margin: 16upx 7upx 0 108upx;
		float: left;
	}
	.img-text{
		font-size: 27upx;
		color: white;
		float: left;
	}
	.img-fpx{
		text-align: center;
		font-size: 50upx;
		color: #FFEFC3;
	}
</style>
