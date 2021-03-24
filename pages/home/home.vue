<template>
	<view>
		<view>数据绑定</view>
		<view>{{msg}}</view>
		<view>{{1+1}}</view>
		<view>{{"你好"+ "世界"}}</view>
		<view>{{flag ? '这是反话-我是假的': '这是反话-我是真的'}}</view>
		<image :src="imgUrl"></image>
		<view v-for="(item, index) in arr" :key="item.id" class="itemObject">
			<text>序号:{{index}}</text> 
			<text>姓名:{{item.name}}</text> 
			<text>年龄:{{item.age}}</text>
		</view>
		<view class="box">
			<button type="primary" v-on:click="clickHandler(20, $event)">点击按钮</button>
		</view>
	</view>
</template>

<script>
	export default {
		data:function () {
			return {
				msg: 'hello',
				flag: false,
				imgUrl: 'https://www.baidu.com/img/flexible/logo/pc/result.png',
				arr: [
					{
						name: '张三',
						age: 20,
						id: 0
					},
					{
						name: '李四',
						age: 25,
						id: 1
					},
					{
						name: '王五',
						age: 30,
						id: 2
					},
					{
						name: '赵柳',
						age: 35,
						id: 3
					}
				]
			}
		},
		methods:{
			clickHandler (num,e) {
				console.log('点击按钮', num, e)
			}
		}
	}
</script>

<style lang="scss">
	.itemObject {
		margin-top: 50rpx;
		text {
			margin: 0 10rpx;
		}
	}
	.box {
		margin-top: 10rpx;
	}
</style>
