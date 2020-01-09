<template>
	<view>
		<swiper-tab-head :tabIndex="tabIndex" @ontabtap="ontabtap"></swiper-tab-head>

		<!-- <block v-for="(item, index) in 10" :key="index">
			<index-list></index-list>
		</block> -->

		<swiper
			class="swiper-box"
			:current="tabIndex"
			:style="{ height: swiperheight + 'px' }"
			@change="tabChange"
		>
			<swiper-item v-for="(item, index) in 9" :key="index">
				<scroll-view scroll-y class="list">
					<block v-for="(litem, lindex) in index + 1" :key="lindex"><index-list></index-list></block>
				</scroll-view>
			</swiper-item>
		</swiper>
	</view>
</template>

<script>
import swiperTabHead from '@/components/swiper-tab-head.vue'
import indexList from '@/components/index-list.vue'

export default {
	components: {
		swiperTabHead,
		indexList
	},
	data() {
		return {
			scroll: 0,
			swiperheight: 0,
			tabIndex: 0
		}
	},
	onLoad() {
		uni.getSystemInfo({
			success: res => {
				console.log(res.windowHeight)
				console.log(res.windowHeight - uni.upx2px(100))
				let height = res.windowHeight - uni.upx2px(100)
				this.swiperheight = height
			}
		})
	},
	// 设置滚动隐藏 TabBar
	// onPageScroll(e) {
	// 	if (this.scroll > e.scrollTop) {
	// 		uni.showTabBar({
	// 			animation: true
	// 		})
	// 	} else {
	// 		uni.hideTabBar({
	// 			animation: true
	// 		})
	// 	}
	// 	this.scroll = e.scrollTop
	// },
	methods: {
		ontabtap(index) {
			this.tabIndex = index
		},
		// 滑动事件
		tabChange(e) {
			this.tabIndex = e.detail.current
		}
	}
}
</script>

<style lang="scss" scoped>
.swiper-box {
	scroll-view {
		height: 100%;
	}
}
</style>
