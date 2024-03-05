<template>
	<view>
		<img class = "userPortrait" :src="imgSrc"/>
		<view>
			<button>打开弹窗</button>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				imgSrc:"../../static/elderUser.png",
				show:false
			};
		},
		methods:{
		}

		
	}
</script>

<style lang="scss">
.userPortrait{
	width: 400rpx;
	border-radius: 100%;
	display: block;
	margin-top: 100rpx;
	margin-left: auto;
	margin-right: auto;
	box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
	
}
</style>
