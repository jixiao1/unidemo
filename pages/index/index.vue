<template>
	<view class="content">
		<!-- <image class="logo" src="/static/logo.png"></image>
		<view class="text-area">
			<text class="title">{{title}}</text>
		</view> -->
		<test v-if="flag" :title="title" @getson="getSon"></test>
		<view>子组件给父组件传的值是: {{content}}</view>
		<button type="default" @click="tabComponents">切换组件</button>
		<testa></testa>
		<testb></testb>
		<view>
		   <uni-calendar 
		       ref="calendar"
		       :insert="false"
		       @confirm="confirm"
		        />
		        <button @click="open">打开日历</button>
		</view>
		<view>{{time}}</view>
	</view>
</template>

<script>
	import test from '../../components/test.vue'
	import testa from '../../components/a.vue'
	import testb from '../../components/b.vue'
	import uniCalendar from '../../components/uni-calendar/uni-calendar.vue'
	export default {
		data() {
			return {
				title: 'Hello',
				flag: true,
				content: '',
				time: ''
			}
		},
		onLoad() {
		  console.log('onLoad')
		},
		onShow() {
			console.log('onShow')
		},
		onReady() {
			console.log('onReady')
		},
		onHide() {
			console.log('onHide')
		},
		methods: {
            tabComponents () {
				this.flag = !this.flag
			},
			getSon (data) {
				console.log(data)
				this.content = data
			},
			 open(){
			            this.$refs.calendar.open();
			        },
			        confirm(e) {
			            console.log(e.fulldate);
						this.time = e.fulldate
			        }
		},
		components:{
			test,
			testa,
			testb,
			uniCalendar
		}
	}
</script>

<style>
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}

	.logo {
		height: 200rpx;
		width: 200rpx;
		margin-top: 200rpx;
		margin-left: auto;
		margin-right: auto;
		margin-bottom: 50rpx;
	}

	.text-area {
		display: flex;
		justify-content: center;
	}

	.title {
		font-size: 36rpx;
		color: #8f8f94;
	}
</style>
