<template>
	<view class="box">
		下拉率性
		<button type="default" @click="get">发送get请求</button>
		<button type="default" @click="setStoreage">数据存储</button>
		<button type="default" @click="getStorasge">获取数据</button>
		<button type="default" @click="removeStorage">删除数据</button>
		<view class="content"
		 v-for="(item, index) in arr">
			{{item}}
		</view>
		<view class="BTN">
			<!-- <button type="primary" @click="methodClick">点击下拉刷新</button> -->
		</view>
	</view>
</template>

<script>
	export default {
		data () {
			return {
				arr: ['前端','JAVA','UI','测试','大数据','前端','JAVA','UI','测试','大数据']
			}
		},
		// 下拉刷新
		onPullDownRefresh() {
			console.log(111)
			setTimeout(() => {
				this.arr = ['前端','JAVA','UI','测试','大数据']
				uni.stopPullDownRefresh()
			}, 2000)
		},
		onReachBottom() {
					console.log('页面触底了')
					this.arr = [...this.arr,...['JAVA','UI','前端','测试','大数据']]
				},
		methods:{
			methodClick () {
				uni.startPullDownRefresh({
					
				})
			},
			// 发送get请求
			get () {
				uni.request({
					url:"http://localhost:8082/api/getlunbo",
					method:	"GET",
					success(res) {
						console.log(res)
					}
				})
			},
			// 数据存储
			setStoreage () {
				// uni.setStorage({
				// 	key:"id",
				// 	data: 100,
				// 	success() {
				// 		console.log('存储成功')
				// 	}
				// })
				uni.setStorageSync("id", 1000)
			},
			// 获取数据
			getStorasge () {
				// uni.getStorage({
				// 	key:"id",
				// 	success:function(data) {
				// 		console.log("获取数据", data.data)
				// 	}
				// })
				const value = uni.getStorageSync("id")
				// console.log(value)
				if (value) {
					console.log(value);
				}
			},
			// 删除数据
			removeStorage () {
				// uni.removeStorage({
				// 	key:"id",
				// 	success() {
				// 		console.log("删除成功")
				// 	}
				// })
				uni.removeStorageSync("id")
			}
		}
	}
</script>

<style lang="scss">
	.content {
		height: 400px;
		line-height: 400px;
	}
</style>
