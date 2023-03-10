<template>
	<view>
		<view class="flex">
			<view :class="['box',{'dark':isActive}]" @tap="handleTab(true)">
				菜单1
			</view>
			<view :class="['box',{'dark':!isActive}]" @tap="handleTab(false)">
				菜单2
			</view>
		</view>
		<view class="box cont margin" v-if="isActive">
			内容1
		</view>
		<view class="box cont margin" v-if="!isActive">
			内容2
		</view>
		<view class="flex">
			<view 
			v-for="(item,index) in tabsArr"
			 :class="['box',{'dark':index==tabIdx}]"
			 @tap="tabIdx=index"
			 >
			{{item}}
			</view>	
		</view>
		<view 
		v-for="(item,index) in tabsArr"  
		class="box cont margin"
		v-show="index==tabIdx"
		>
			这是{{item}}的内容
		
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				isActive:false,
				tabsArr:['首页','新闻','产品','联系我们'],
				tabIdx:0
			}
		},
		methods: {
			handleTab(bool){
				this.isActive=bool
			}
		}
	}
</script>

<style>
.flex{
	display: flex;
	justify-content: center;
}
.box{
	padding: 15upx 25upx;
	color: white;
	background-color: #85929E;
}
.dark{
	background-color: #34495E !important ;
}
.cont{
	height: 150upx;
	background-color: #85929E ;
	color: white;
	padding:20upx 0 0 10upx
}
.margin{
	margin: 8upx 5upx;
}
</style>
