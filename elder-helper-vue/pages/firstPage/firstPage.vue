<template>
	<view>
		<img class = "userPortrait" :src="imgSrc"/>
		<view>
			<button @click="open">打开弹窗</button>
			<uni-popup ref="popup" type="right">底部Popup</uni-popup>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				imgSrc:"../../static/elderUser.jpg",
				show:false
			};
		},
		methods:{
			open(){
			  // 通过组件定义的ref调用uni-popup方法 ,如果传入参数 ，type 属性将失效 ，仅支持 ['top','left','bottom','right','center']
			  this.$refs.popup.open('right')
			},
			popshow(){
				this.show = !this.show
			}
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
