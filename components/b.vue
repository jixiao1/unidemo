<template>
	<view class="content">
		a于b的通信
		<text>{{num}}</text>
	</view>
</template>

<script>
	export default {
		data () {
			return {
				num: 0
			}
		},
		created() {
			uni.$on('getsona', (num) => {
				this.num += num
			})
		}
	}
</script>

<style>
</style>
