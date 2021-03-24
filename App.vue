<script>
	export default {
		onLaunch: function() {
			//  App的生命周期
			console.log('App Launch')
		},
		onShow: function() {
			console.log('App Show')
		},
		onHide: function() {
			console.log('App Hide')
		},
		onError: function(error) {
			console.log('error')
		}
	}
</script>

<style>
	@import url("./static/fonts/iconfont.css");
	/*每个页面公共css */
	.box1 {
		background-color: #4CD964;
	}
</style>
