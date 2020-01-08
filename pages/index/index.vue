<template>
	<view>
		<view class="index-list" v-for="(item, index) in 10" :key="index">
			<view class="index-list1 u-f-ac u-f-jsb">
				<view class="u-f-ac">
					<image src="../../static/demo/userpic/14.jpg" mode="widthFix" lazy-load></image>
					昵称
				</view>
				<view class="u-f-ac">
					<view class="icon iconfont icon-zengjia"></view>
					关注
				</view>
			</view>
			<view class="index-list2">我是标题</view>
			<view class="index-list3 u-f-ajc">
				<image src="../../static/demo/datapic/29.jpg" mode="widthFix" lazy-load></image>
			</view>
			<view class="index-list4 u-f-ac u-f-jsb">
				<view class="u-f-ac">
					<view class="u-f-ac">
						<view class="icon iconfont icon-icon_xiaolian-mian"></view>
						987
					</view>
					<view class="u-f-ac">
						<view class="icon iconfont icon-kulian"></view>
						10
					</view>
				</view>
				<view class="u-f-ac">
					<view class="u-f-ac">
						<view class="icon iconfont icon-pinglun1"></view>
						34
					</view>
					<view class="u-f-ac">
						<view class="icon iconfont icon-zhuanfa"></view>
						7
					</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
export default {
	data() {
		return {}
	},
	onLoad() {},
	methods: {}
}
</script>

<style lang="scss" scoped>
.index-list {
	padding: 20upx;
	border-bottom: 1upx solid #eeeeee;
}
.index-list1 > view:first-child {
	color: #999999;
}
.index-list1 > view:first-child image {
	width: 85upx;
	height: 85upx;
	border-radius: 100%;
	margin-right: 15upx;
}
.index-list1 > view:last-child {
	background: #f4f4f4;
	border-radius: 5upx;
	padding: 0 10upx;
}
.index-list2 {
	padding-top: 15upx;
	font-size: 32upx;
}
.index-list3 {
	// position: relative;
	padding-top: 15upx;
}
.index-list3 > image {
	width: 100%;
	border-radius: 20upx;
}
.index-list4 view {
	color: #d5d5d5;
}
.index-list4 {
	padding: 15upx 0;
}
.index-list4 > view > view > view,
.index-list4 > view > view:first-child {
	margin-right: 15upx;
}
</style>
