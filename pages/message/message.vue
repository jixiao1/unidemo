<template>
	<view>
		<!-- <view>信息页</view> -->
		<button type="primary" @click="uploadPLAY">上传图片</button>
		<image v-for="item in ImgArr" :src="item" @click="preview(item)"></image>
		<!-- #ifdef H5 -->
		<view>我希望这个在h5中可以看见</view>
		<!-- #endif -->
		<!-- #ifdef MP-WEIXIN -->
		<view>我希望这个在微信中可以看见</view>
		<!-- #endif -->
	</view>
</template>

<script>
	export default {
		data:function() {
			return {
				ImgArr: []
			}
		},
		onLoad(option) {
			console.log('option', option)
		},
		methods:{
			// 加载图片的方法
			uploadPLAY () {
				uni.chooseImage({
					count: 5,
					success: res=> {
						console.log("上传图片", res)
						this.ImgArr = res.tempFilePaths
						console.log(this.ImgArr)
					}
				})
			},
			// 展示图片 预览图片。
			preview (current) {
				console.log(current)
				uni.previewImage({
					current,
					urls:this.ImgArr,
					indicator:Number,
					loop:true
				})
			}
		},
	    onLoad() {
			// #ifdef H5
	    	console.log('我希望这个在h5中可以看见');
			//  #endif
			// #ifdef MP-WEIXIN
			console.log('我希望这个在微信中可以看见');
			// #endif
	    }
	}
</script>

<style>
	/* #ifdef H5 */
	view {
		color: #4CD964;
	}
	/* #endif */
	/* #ifdef MP-WEIXIN */
	view {
		color: #DD524D;
	}
	/* #endif */
</style>
