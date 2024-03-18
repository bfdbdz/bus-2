<template>
	<view class="login">
		<!-- 背景图 -->
		<view class="login-img">
			<image src="../../static/mine_icons/login-back.png" class="login-back" mode="widthFix"></image>
		</view>
		<view class="login-continer">
			<!-- 欢迎登录 -->
			<view class="login-text">
				<text class="login-text">欢迎登录</text>
			</view>
			<!-- 登录输入框 -->
			<view class="login-on">

				<view class="login-input">

					<input class="uni-input-1" type="number" placeholder="学号/工号" />
					<view class="wrapper">
						<view class="uni-input-wrapper">
							<input class="uni-input-2" placeholder="请输入密码" :password="showPassword" />
							<!-- <text class="uni-icon" :class="[! showPassword ? 'uni-eye-active' : '']"
						@click="changePassword"></text> -->
							<image class="uni-icon"
								:src="[!showPassword ? '../../static/mine_icons/eye-active.png' : '../../static/mine_icons/eye.png']"
								@click="changePassword" mode="heightFix"></image>
						</view>
					</view>
				</view>
			</view>
			<view class="button">
				<button class="login-button">登录</button>
			</view>
			<view class="register">
				<text class="register-text" @loginclick="toRegister">还没有账号？去注册</text>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		name: "mine-login",
		data() {
			return {
				showPassword: true
			};
		},
		methods: {
			changePassword: function() {
				this.showPassword = !this.showPassword;
			},
			toRegister: function() {
				// console.log("okk")
				this.$emit('loginclick')
			}
		}
	}
</script>

<style lang="scss">
	.login-img {
		display: flex;
		justify-content: center;

		.login-back {
			width: 80%;
		}
	}



	.login-continer {
		height: 540rpx;
		background: rgba(101, 135, 181, 0.4);
		margin-top: 30rpx;
		margin-left: 50rpx;
		margin-right: 50rpx;
		border-radius: 20rpx;

		.login-text {
			font-size: 50rpx;
			text-align: center;
			padding-top: 50rpx;
			margin-bottom: 50rpx;
		}

		.login-on {
			display: flex;
			justify-content: center;

			.uni-input-1 {
				width: 500rpx;
				height: 50rpx;
				border-bottom: 1rpx solid grey;
				padding-bottom: 10rpx;
				// border-radius: 6rpx;
				margin-bottom: 30rpx;
			}
		}

		.button {
			display: flex;
			justify-content: center;

			.login-button {
				background-color: #6587b5;
				margin-top: 50rpx;
				width: 300rpx;
			}
		}


	}

	.uni-input-wrapper {
		width: 500rpx;
		// height: 50rpx;
		display: flex;
		justify-content: space-between;
		border-bottom: 1rpx solid grey;
		padding-bottom: 10rpx;

		.uni-icon {
			height: 50rpx;
		}
	}

	.register {
		display: flex;
		justify-content: center;

		.register-text {
			font-size: 25rpx;
			color: gray;
		}
	}
</style>