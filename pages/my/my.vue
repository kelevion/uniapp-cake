<template>
    <view>
		<view class="cont">	
	</view>
     <view class="margin bg-fff">
		 <view class="avatar">
		 		<u-avatar 
				:src="src"
				size="80"
				></u-avatar>
				<text class="nickname fs-30">{{nickname}}</text>
		 	</view>

     	<u-grid
     	        :border="false"
     	        @click="click"
     			col="4"
     	>
     	    <u-grid-item
     	            v-for="(baseListItem,baseListIndex) in baseList"
     	            :key="baseListIndex"
     				class="bg-fff"
     	    >
     	        <u-icon
     	                :customStyle="{paddingTop:20+'rpx'}"
     	                :name="baseListItem.name"
     	                :size="28"
     	        ></u-icon>
     	        <text class="grid-text">{{baseListItem.title}}</text>
     	    </u-grid-item>
     	</u-grid>
     	<u-toast ref="uToast" />
     </view>
    </view>
</template>

<script>
    export default {
        data() {
            return {
				nickname:"无头像",
                baseList: [{
                    name: 'file-text-fill',
                    title: '我的订单'
                    },
                    {
                        name: 'car-fill',
                        title: '待收货'
                    },
                    {
                        name: 'rmb-circle-fill',
                        title: '待付款'
                    },
					{
					    name: 'integral-fill',
					    title: '会员等级'
					},
					{
					    name: 'car-fill',
					    title: '待收货'
					},
					{
					    name: 'rmb-circle-fill',
					    title: '待付款'
					},
					{
					    name: 'integral-fill',
					    title: '会员等级'
					},
					{
					    name: 'integral-fill',
					    title: '会员等级'
					},
                ],
				src: 'http://pic2.sc.chinaz.com/Files/pic/pic9/202002/hpic2119_s.jpg'

            }
        },
        methods: {
            click(name) {
                this.$refs.uToast.success(`点击了第${name}个`)
            }
        }
    }
</script>

<style lang="scss">
	.cont{
		background-color: #f6f6f6;
		height: 200rpx;
	}
    .grid-text {
        font-size: 16px;
        color: #909399;
        padding: 10rpx 0 20rpx 0rpx;
        /* #ifndef APP-PLUS */
        box-sizing: border-box;
        /* #endif */
    }
	.margin{
		margin:20rpx;
	}
	.avatar{
		display: flex;
		justify-content: center;
		flex-direction: column;
		transform: translateY(-50%);
		
	}
	
	.avatar>view{
		transform: translateX(135px);
	}
	
	.nickname{
		text-align: center;
	}
</style>