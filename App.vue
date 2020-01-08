<script>
export default {
	onLaunch: function() {
		console.log('App Launch')
	},
	onShow: function() {
		console.log('App Show')
	},
	onHide: function() {
		console.log('App Hide')
	},
	methods: {
		/**
		 * 处理推送消息
		 */
		handlePush() {
			// #ifdef APP-PLUS
			const _self = this
			const _handlePush = function(message) {
				// 获取自定义信息
				// let payload = message.payload
				// try {
				// 	// JSON解析
				// 	payload = JSON.parse(payload)
				// 	// 携带自定义信息跳转应用页面
				// 	uni.navigateTo({
				// 		url: '/pages/xxx?data=' + JSON.stringify(payload)
				// 	})
				// } catch (e) {}
				plus.runtime.setBadgeNumber(1)
				console.log(message)
			}
			// 事件处理
			plus.push.addEventListener('click', _handlePush)
			plus.push.addEventListener('receive', _handlePush)
			// #endif
		}
	}
}
</script>

<style>
/*每个页面公共css */
/* 引入官方css库 */
@import './common/uni.css';
/* 引入自定义图标库 */
@import './common/icon.css';
/* 引入动画库 */
@import './common/animate.css';
/* 公共样式 */
@import './common/common.css';
</style>
