<template>
	<view class="login">
		<text>这是登录页，希望从这里发芽生长</text>
		<form @submit="formSubmit" @reset="formReset">
			<input class="uni-input" name="input" v-model="formData.Account" placeholder="请输入账号" />
			<input class="uni-input" name="input" type="password" v-model="formData.Password" placeholder="请输入密码" />
		</form>
		<button type="primary" class="btn-top" @click="formSubmit">登录</button>
	</view>
</template>

<script>
	import md5 from 'js-md5';
	export default {
		name: "login",
		data() {
			return {
				formData: {
					Account: "",
					Password: ""
				}
			}
		},
		methods: {
			formSubmit() {
				let formData = _.extend({}, this.formData);
				formData.Password = md5(formData.Password);
				console.log(formData);
			},
			formReset() {
				this.formData = {
					Account: "",
					Password: ""
				};
			}
		}
	}
</script>

<style lang="scss">
	.login {
		width: 100%;
		height: calc(100vh - 44px);
		background: #E8E8E8;
		.btn-top {
			margin: 10px 40px;
		}
	} 
</style>
