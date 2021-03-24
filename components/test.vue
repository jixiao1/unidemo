<template>
	<view>
		<view class="test">
			testtest组件{{num}}
		</view>
		<view>父组件给子组件传的值是: {{title}}</view>
		<button type="default" @click="getFather">子组件给父组件传值</button>
	</view>
</template>

<script>
	export default {
		data () {
			return {
				num: 100,
				setId: null
			}
		},
		props:['title'],
		beforeCreate() {
			console.log("初始化数据")
			console.log(this.num)
		},
		created() {
			console.log(this.num)
			// this.setId = setInterval(() => {
			// 	console.log("定时器启动了")
			// }, 100)
		},
		beforeMount() {
			// console.log('dom节点产生', document.querySelector(".test"))
		},
		mounted () {
			// console.log('dom节点产生', document.querySelector(".test"))
		},
		beforeUpdate() {
			
		},
		updated() {
			
		},
		beforeDestroy() {
			// console.log('DOM销毁了')
		},
		destroyed () {
			// console.log('DOM销毁了')
		   // clearInterval(this.setId)
		},
		methods:{
			getFather () {
				this.$emit('getson', '儿子给爸爸的东西')
			}
		},
		components:{}
	}
</script>

<style lang="scss">
	.test {
		font-size: 50px;
		color: red;
	}
</style>
