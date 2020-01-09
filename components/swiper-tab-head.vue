<template>
	<view class="uni-tab-bar">
		<scroll-view scroll-x class="uni-swiper-tab">
			<view
				class="swiper-tab-list"
				v-for="(tab, index) in tabBars"
				:key="tab.id"
				:class="tabIndex === index ? 'active' : ''"
				@tap="ontabtap(index)"
			>
				{{ tab.name }}
				<view class="swiper-tab-line"></view>
			</view>
		</scroll-view>
	</view>
</template>

<script>
export default {
	props: {
		tabIndex: Number
	},
	data() {
		return {
			// tabIndex: 0,
			tabBars: [
				{
					name: '关注',
					id: 'guanzhu'
				},
				{
					name: '推荐',
					id: 'tuijian'
				},
				{
					name: '体育',
					id: 'tiyu'
				},
				{
					name: '热点',
					id: 'redian'
				},
				{
					name: '财经',
					id: 'caijing'
				},
				{
					name: '娱乐',
					id: 'yule'
				},
				{
					name: '军事',
					id: 'junshi'
				},
				{
					name: '历史',
					id: 'lishi'
				},
				{
					name: '本地',
					id: 'bendi'
				}
			]
		}
	},
	onLoad() {
		console.log('onload');
	},
	methods: {
		ontabtap(index) {
			this.$emit('ontabtap', index)
		}
	}
}
</script>

<style lang="scss" scoped>
.uni-swiper-tab {
	border-bottom: 1upx solid #ffffff;

	.swiper-tab-list {
		color: #969696;
		font-weight: bold;
	}

	.active {
		color: #343434;
		
		.swiper-tab-line {
			// border-bottom: 6upx solid #fede33;
			// width: 70upx;
			// margin: auto;
			// border-top: 6upx solid #fede33;
			// border-radius: 20upx;
			
			margin: 0 auto;
			width: 70upx;
			height: 12upx;
			background-color: #FFE933;
			border-radius: 20upx;
		}
	}
}
</style>
