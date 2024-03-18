<template>
	<view class="register">

		<view class="register-top">
			<!-- 背景图 -->
			<image class="register-back" src="../../static/mine_icons/register.png" mode="widthFix"></image>
			<view class="register-text">
				<text class="text">Hello!</text>
			</view>
		</view>
		<!-- 注册信息 -->
		<view class="register-continer">
			<!-- 输入框 -->
			<view class="register-on">
				<view class="register-input">

					<input class="uni-input-0" focus placeholder="姓名" />

					<input class="uni-input-1" type="number" focus="true" maxlength="11" placeholder="请输入11位手机号" />

					<view class="wrapper">
						<view class="uni-input-wrapper">
							<input class="uni-input-2" placeholder="请输入密码" :password="showPassword1" />
							<image class="uni-icon"
								:src="[!showPassword1 ? '../../static/mine_icons/eye-active.png' : '../../static/mine_icons/eye.png']"
								@click="changePassword1" mode="heightFix"></image>
						</view>
					</view>

					<view class="wrapper">
						<view class="uni-input-wrapper">
							<input class="uni-input-2" placeholder="请再次输入密码确认" :password="showPassword2" />
							<image class="uni-icon"
								:src="[!showPassword2 ? '../../static/mine_icons/eye-active.png' : '../../static/mine_icons/eye.png']"
								@click="changePassword2" mode="heightFix"></image>
						</view>
					</view>

				</view>
			</view>
		</view>
		<view class="button">
			<button class="register-button" @loginclick="toLogin">注册</button>
		</view>
	</view>
	</view>
</template>

<script>
	export default {
		name: "mine-register",
		data() {
			return {
				showPassword1: true,
				showPassword2: true
			};
		},
		methods: {
			changePassword1: function() {
				this.showPassword1 = !this.showPassword1;
			},
			changePassword2: function() {
				this.showPassword2 = !this.showPassword2;
			},
			toLogin: function() {
				// console.log("okk")
				this.$emit('loginclick')
			}
		}
	}
</script>

<style lang="scss">
	// .register-img {
	// 	// display: flex;
	// 	// justify-content: center;


	// }
	.register-top {
		display: flex;
		justify-content: space-evenly;

		.register-back {
			width: 45%;
			margin-top: 10rpx;
			margin-left: 20rpx;
		}

		.register-text {
			display: flex;
			justify-content: center;
			align-items: center;

			.text {
				color: rgba(101, 135, 181, 0.8);
				font-size: 100rpx;
				text-shadow: 5rpx 5rpx 1rpx #6587b5;
				font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
				// font-weight: bold;
			}


		}
	}


	.register-continer {
		height: 450rpx;
		background: rgba(101, 135, 181, 0.4);
		margin-top: 10rpx;
		margin-left: 50rpx;
		margin-right: 50rpx;
		border-radius: 20rpx;

		.register-on {
			display: flex;
			justify-content: center;

			.uni-input-0 {
				width: 500rpx;
				height: 50rpx;
				border-bottom: 1rpx solid grey;
				padding-top: 40rpx;
				padding-bottom: 10rpx;
				margin-bottom: 30rpx;
			}

			.uni-input-1 {
				width: 500rpx;
				height: 50rpx;
				border-bottom: 1rpx solid grey;
				padding-bottom: 10rpx;
				margin-bottom: 30rpx;
			}
		}
	}

	.uni-input-wrapper {
		width: 500rpx;
		display: flex;
		justify-content: space-between;
		border-bottom: 1rpx solid grey;
		padding-bottom: 10rpx;
		margin-bottom: 30rpx;

		.uni-icon {
			height: 50rpx;
		}
	}

	.button {
		display: flex;
		justify-content: center;

		.register-button {
			background-color: #6587b5;
			margin-top: 50rpx;
			width: 300rpx;
		}
	}
</style>