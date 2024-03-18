<template>
	<view>
		<mine-login @loginclick="toRegister" v-if="pag===0"></mine-login>
		<mine-register @loginclick="toLogin" v-if="pag===1"></mine-register>

		<mine-userinfo></mine-userinfo>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				pag: 0 //pag为0——登录组件，pag为1——注册组件，pag为2——用户信息组件
			};
		},
		methods: {
			toRegister: function() {
				// console.log("nono")
				this.pag = 1
				// console.log(this.pag)
			},
			toLogin: function() {
				this.pag = 0
			}
		}
	}
</script>

<style lang="scss">

</style>