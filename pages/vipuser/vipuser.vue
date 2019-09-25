<template>
	<view class="content">
		<view class="backimg">
			<image class="bgimg-all" src="../../static/vip/vipbgimg1.png"></image>
			<image class="bgimg-box" src="../../static/vip/tuoyuan.png"></image>
			<view class="img-top">
				<view style="width: 78%;font-size: 34upx;display: flex;display: -webkit-flex;flex-wrap: nowrap;">
					<view style=""><image src="../../static/vip/kefutouxiang.png" style="width: 90upx;height: 90upx;border-radius: 50%;"></image></view>
					<view style="display: flex;display: -webkit-flex;flex-direction: column;width: 70%;margin-left: 12upx;">
						<text style="margin-top: 6upx;">小川UU</text>
						<text style="font-size: 27upx;">您还不是VIP会员</text>
					</view>
				</view>
				<view style="width: 22%;font-size: 27upx;line-height: 100upx;">立即开通 ></view>
			</view>
			<view class="img-content">
				<view class="img-content-left">
					<view class="img-gdx">
						<image class="img-img" src="../../static/vip/shegbi.png"></image>
						<text class="img-text">省币</text>
					</view>
					<view class="img-fpx">2222</view>
				</view>
				<view class="img-content-right">
					<view class="img-gdx">
						<image class="img-img" src="../../static/vip/jingbi.png"></image>
						<text class="img-text">金币</text>
					</view>
					<view class="img-fpx">2222</view>
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
			<button class="btn-vip">立即成为VIP会员</button>
			<view class="monthpack">
				<view class="f-header m-t">
					<image src="/static/vip/yuelibaojuan.png"></image>
					<view class="tit-box">
						<text class="tit">月礼包</text>
						<text class="tit2">每月免费领取4张价值10元的无门槛优惠券</text>
					</view>
				</view>
				<scroll-view class="floor-list" scroll-x>
					<view class="scoll-wrapper">
						<view v-for="(item, index) in goodsList1" :key="index" class="floor-item" @click="navToDetailPage(item)">
							<view class="left-scroll">
								<view style="width: 100%;font-size: 17px;margin: 40upx 0 0 50upx;color: black;">
									¥
									<text style="font-size: 25px;">{{ item.price }}</text>
								</view>
								<view style="width: 100%;font-size: 30upx;color: #AFAFAF;margin-left: 30upx;">{{ item.title }}</view>
							</view>
							<image :src="item.image" mode="aspectFill" class="img-srcoll"></image>
							<view style="position: absolute;margin-left: 200upx;margin-top: 45upx;">
								<text style="width: 100%;font-size: 38upx;color: white;margin: 0 0 0 80upx;">{{ item.content }}</text>
								<view style="width: 100%;font-size: 28upx;color: white;margin-left: 30upx;">
									有效期至：
									<text>{{ item.data }}</text>
								</view>
								<button
									type="primary"
									style="height: 50upx;line-height: 50upx;background: white;color: black;width: 160upx;font-size: 28upx;border-radius: 20upx;margin-left: 200upx;margin-top: 10upx;"
								>
									立即领取
								</button>
							</view>
						</view>
					</view>
				</scroll-view>
			</view>
			<view class="f-header m-t" style="margin-top: 15upx;">
				<image src="/static/vip/yuelibaojuan.png"></image>
				<view class="tit-box">
					<text class="tit">免费试用</text>
					<text class="tit2">每月免费领取一件商品试用，全年可领取12件</text>
				</view>
				<text class="yticon icon-you"></text>
			</view>
			<view class="guess-section">
				<view v-for="(item, index) in goodsList" :key="index" class="guess-item" @click="navToDetailPage(item)">
					<view class="image-wrapper"><image :src="item.image" mode="aspectFill"></image></view>
					<text class="title clamp">{{ item.title }}</text>
					<view style="width: 100%;display: flex;flex-wrap: nowrap;">
						<text class="price" style="line-height: 50upx;">￥{{ item.price }}</text>
						<text class="price" style="color: #B7B7B7;font-size: 28upx;text-decoration: line-through;margin-right: 10upx;line-height: 50upx;">
							￥{{ item.oldprice }}
						</text>
						<button :class="item.statusfree == 0 ? 'btn-yuemian' : 'btn-yumianyuan'">{{ item.statusfree == 0 ? '免费试用' : '已领取' }}</button>
					</view>
				</view>
			</view>
			<view class="f-header m-t" style="margin-top: 15upx;">
				<image src="/static/vip/yuelibaojuan.png"></image>
				<view class="tit-box">
					<text class="tit">会员专享折扣</text>
					<text class="tit2">全场产品自购省钱1%-25%,全球工厂店内产品5折</text>
				</view>
				<text class="yticon icon-you"></text>
			</view>
			<view class="guess-section" style="margin-bottom: 100upx;">
				<view v-for="(item, index) in goodsList" :key="index" class="guess-item" @click="navToDetailPage(item)">
					<view class="image-wrapper"><image :src="item.image" mode="aspectFill"></image></view>
					<text class="title clamp">{{ item.title }}</text>
					<view style="width: 100%;display: flex;flex-wrap: nowrap;">
						<text class="price" style="line-height: 50upx;">￥{{ item.price }}</text>
						<text class="price" style="color: #B7B7B7;font-size: 28upx;text-decoration: line-through;margin-right: 10upx;line-height: 50upx;">
							￥{{ item.oldprice }}
						</text>
						<button class="btn-yuemian'">专享价</button>
					</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
export default {
	data() {
		return {
			goodsList1: [
				{
					image: '/static/vip/yuelibaored.png',
					title: '满十元使用',
					price: 10,
					content: '无门槛优惠券1',
					data: '2019-10-10 12:00'
				},
				{
					image: '/static/vip/yuelibaoyellow.png',
					title: '满十元使用',
					price: 10,
					content: '无门槛优惠券2',
					data: '2019-10-10 12:00'
				},
				{
					image: '/static/vip/yuelibaogreen.png',
					title: '满十元使用',
					price: 10,
					content: '无门槛优惠券3',
					data: '2019-10-10 12:00'
				}
			],
			goodsList: []
		};
	},
	onLoad() {
		this.loadData();
	},
	methods: {
		navToDetailPage(item) {
			console.log(item);
		},
		async loadData() {
			let carouselList = await this.$api.json('carouselList');
			this.titleNViewBackground = carouselList[0].background;
			this.swiperLength = carouselList.length;
			this.carouselList = carouselList;

			let goodsList = await this.$api.json('goodsList');
			this.goodsList = goodsList || [];
		}
	}
};
</script>

<style lang="scss">
page,
.content {
	height: 100%;
	background-color: #f8f8f8;
}

.content {
	display: flex;
}
.backimg {
	width: 100%;
}
.bgimg-all {
	position: relative;
	height: 850upx;
	width: 100%;
}
.bgimg-box {
	width: 90%;
	position: absolute;
	left: 5%;
	top: 0;
	height: 310upx;
}
.img-top {
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
.img-content {
	width: 85%;
	position: absolute;
	height: 150upx;
	left: 5%;
	top: 110upx;
	background: rgba(251, 251, 251, 0.1);
	margin: 20upx;
	display: flex;
	flex-wrap: nowrap;
}
.img-content-left {
	width: 50%;
	height: 100%;
	display: flex;
	display: -webkit-flex;
	flex-direction: column;
}

.img-content-right {
	width: 50%;
	height: 100%;
	display: flex;
	display: -webkit-flex;
	flex-direction: column;
}
.vip-text {
	font-size: 16px;
	color: #fceec2;
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
	flex-wrap: wrap;
	padding: 30upx 22upx;
	width: 100%;
	.cate-item {
		display: flex;
		flex-direction: column;
		align-items: center;
		font-size: $font-sm + 2upx;
		color: white;
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
.btn-vip {
	width: 82%;
	height: 80upx;
	position: absolute;
	top: 730upx;
	background: linear-gradient(70deg, #fdebbf 0%, #e9ca74 100%);
	left: 9%;
	border-radius: 55upx;
	color: black;
}
.img-gdx {
	text-align: center;
	height: 70upx;
	line-height: 70upx;
}
.img-img {
	width: 40upx;
	height: 40upx;
	margin: 16upx 7upx 0 108upx;
	float: left;
}
.img-text {
	font-size: 27upx;
	color: white;
	float: left;
}
.img-fpx {
	text-align: center;
	font-size: 50upx;
	color: #ffefc3;
}
.monthpack {
	width: 100%;
	height: 370upx;
	margin-top: 10upx;
	background: white;
}
.f-header {
	display: flex;
	align-items: center;
	height: 140upx;
	padding: 6upx 30upx 8upx;
	background: #fff;
	image {
		flex-shrink: 0;
		width: 80upx;
		height: 80upx;
		margin-right: 20upx;
	}
	.tit-box {
		flex: 1;
		display: flex;
		flex-direction: column;
	}
	.tit {
		font-size: $font-lg + 2upx;
		color: #font-color-dark;
		line-height: 1.3;
	}
	.tit2 {
		font-size: $font-sm;
		color: $font-color-light;
	}
	.icon-you {
		font-size: $font-lg + 2upx;
		color: $font-color-light;
	}
}
.floor-list {
	white-space: nowrap;
}
.scoll-wrapper {
	display: flex;
	align-items: flex-start;
}
.floor-item {
	width: 600upx;
	height: 210upx;
	margin: 0 10upx;
	border-radius: 16upx;
	box-shadow: 10upx 10upx 10upx #c0c4cc;
	display: flex;
	flex-wrap: nowrap;
	border: 1px solid #ebeef5;
	.left-scroll {
		width: 200upx;
		height: 170upx;
		background: white;
	}
	.img-srcoll {
		width: 400upx;
		height: 210upx;
		position: relative;
	}
	.price {
		color: $uni-color-primary;
	}
}
.guess-section {
	display: flex;
	flex-wrap: wrap;
	padding: 0 30upx;
	background: #fff;
	.guess-item {
		display: flex;
		flex-direction: column;
		width: 48%;
		padding-bottom: 40upx;
		&:nth-child(2n + 1) {
			margin-right: 4%;
		}
	}
	.image-wrapper {
		width: 100%;
		height: 330upx;
		border-radius: 3px;
		overflow: hidden;
		image {
			width: 100%;
			height: 100%;
			opacity: 1;
		}
	}
	.title {
		font-size: $font-lg;
		color: $font-color-dark;
		line-height: 80upx;
	}
	.price {
		font-size: $font-lg;
		color: $uni-color-primary;
		line-height: 1;
	}
}
.btn-yuemian {
	height: 50upx;
	line-height: 35upx;
	background: white;
	background: #F1414C;
	width: 140upx;
	font-size: 28upx;
	border-radius: 20upx;
	padding: 10upx;
	color: white;
}
.btn-yumianyuan{
	height: 50upx;
	line-height: 35upx;
	background: white;
	background: #C1C1C1;
	width: 140upx;
	font-size: 28upx;
	border-radius: 20upx;
	padding: 10upx;
	color: white;
}
</style>
