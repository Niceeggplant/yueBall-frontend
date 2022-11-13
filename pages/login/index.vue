<!-- 蓝色简洁登录页面 -->
<template>
	<view class="t-login">
		<!-- 页面装饰图片 -->
		<image class="img-a" src="/static/img/b-1.png"></image>
		<image class="img-b" src="/static/img/b-2.png"></image>
		<!-- 标题 -->
		<view class="t-b">{{ title }}</view>
		<view class="t-b2">{{ subTitle }}</view>

		<button class="cu-btn block bg-green margin-tb-sm lg shadow" @click="getUserInfo">
			微信一键登录
		</button>

	</view>
</template>
<script>
	import {
		isEmpty
	} from '@/utils/verify.js'

	export default {
		data() {
			return {
				title: '约个不咕的球',
				subTitle: '欢迎使用，开始约球吧！',

				uuid: ''
			};
		},
		created() {
        if()
		},
		methods: {

			// 10.67.154.106
			getUserInfo() {
				uni.getUserProfile({
					lang: 'zh_CN',
					desc: '登录',
					success: details => {
						this.userInfo = details.userInfo; //用户信息，微信头像，昵称等等
						// 将用户授权信息存储到本地
						wx.setStorageSync('userinfo', details.userInfo)
						uni.login({
							success(res) {
								uni.request({
									url: 'http://10.67.154.106:3000/login',
									data: {
										code: res.code
									},
									header: {
										'content-type': 'application/json'
									},

									method: 'POST',

									success(res) {
										
										// 将后端返回的token存储到本地
									wx.setStorageSync('token', res)
										console.log(res, '后台数据')
									}
								})
								console.log(details)
								console.log(res.code) //获取到的code
							}
						})
					},
					fail(res) {
						uni.showToast({
							title: '登录授权失败',
							icon: 'none',
						})
					}
				});
			}

		}

		
	};
</script>
<style lang="scss" scoped>
	@import 'index.scss';
</style>
