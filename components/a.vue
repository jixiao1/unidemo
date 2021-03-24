<template>
	<view class="contetyn">
		a组件给b组件传值: <button type="default" @click="getb">传值</button>
	</view>
</template>

<script>
	export default {
		data () {
			return {}
		},
		methods: {
			getb () {
				uni.$emit('getsona', 100) 
			}
		}
	}
</script>

<style>
</style>
