<template>
  <view class="content">
	  <view>导航跳转的学习</view>
	  <navigator url="/pages/detail/detail?id = 80 &name = jixioa">跳转至详情</navigator>
	   <navigator url="/pages/message/message" open-type="switchTab">跳转至信息页面</navigator>
	   <navigator url="/pages/detail/detail" open-type="redirect">跳转到详情页</navigator>
	   
	   <button type="default" @click="goDeail">跳转至详情</button>
	   <button type="default" @click="goMessasge">跳转至信息页面</button>
	    <button type="default" @click="goMessasgeDetail">跳转到详情页</button>
  </view>
</template>

<script>
	export default {
		data:function() {
			return {}
			},
			onUnload () {
				console.log("导航页面卸载了")
			},
			methods:{
				goDeail () {
					uni.navigateTo({
						url: '/pages/detail/detail?id = 300'
					})
				},
				goMessasge () {
					uni.switchTab({
						url:'/pages/message/message'
					})
				},
				goMessasgeDetail () {
					uni.redirectTo({
						url: '/pages/detail/detail'
					})
				}
			}
	}
</script>

<style>
</style>
