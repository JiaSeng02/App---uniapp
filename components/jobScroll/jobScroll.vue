<template>
	<view>
		<view class="job_scroll_box">
			<scroll-view scroll-x="true" class="job_scroll_con_box" >
				<view class="job_scroll_con">
					<view class="job_scroll_info" v-for="(item, index) in list" :key="index">
						<view class="job_scroll_card" :class="item.colors">
							<view class="job_scroll_card_T">{{ item.textT }}</view>
							<view class="job_scroll_card_icon">
								<view class="icon iconfont" :class="item.icon"></view>
							</view>
							<view class="job_scroll_card_des">{{ item.text }}</view>
							<view class="job_scroll_card_btn">免费试学</view>
						</view>
					</view>
				</view>
			</scroll-view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				list: [],
			}
		},
		methods: {
			
		},
		mounted() {
			this.list = require('@/common/jobCourseData.json');
			//console.log(this.list)
		}
	}
</script>

<style lang="scss">
@import "@/common/icofont/icofont/icofont.css";

.job_scroll_box {
	width: 100%;
	margin-bottom: 30px;
	box-sizing: border-box;
	margin-right: 15px;
	
	.job_scroll_con {
		display: flex;
		align-items: center;
		text-wrap: nowrap;
		box-sizing: border-box;
		
		.job_scroll_info {
			width: 225px;
			height: 260px;
			flex-shrink: 0;
			margin: 0 10px;
			
			.job_scroll_card {
				display: flex;
				flex-flow: column;
				box-sizing: border-box;
				align-items: center;
				width: 100%;
				height: 248px;
				background-color: #b0def5;
				border-radius: 5px;
				margin-top: 12px;
				
				.job_scroll_card_T {
					display: flex;
					align-items: center;
					justify-content: center;
					width: 210px;
					height: 38px;
					background-color: #e4f3fb;
					font-size: 16px;
					text-align: center;
					margin-top: -15px;
					border-bottom-left-radius: 25px;
					border-bottom-right-radius: 25px;
					border-top-left-radius: 15px;
					border-top-right-radius: 15px;
				}
				
				.job_scroll_card_icon {
					display: flex;
					align-items: center;
					justify-content: center;
					box-sizing: border-box;
					width: 90px;
					height: 90px;
					background-color: #d3ecf9;
					border-radius: 100px;
					margin: 20px 0 15px;
					
					view {
						font-size: 42px;
						color: #2a83fe;
					}
				}
				
				.job_scroll_card_des {
					display: flex;
					box-sizing: border-box;
					align-items: center;
					font-size: 14px;
				}
				
				.job_scroll_card_btn {
					display: flex;
					box-sizing: border-box;
					align-items: center;
					justify-content: center; 
					width: 118px;
					height: 32px;
					line-height: 32px;
					color: #0a5ea0;
					font-size: 16px;
					border-radius: 34px;
					border: 1px solid #0a5ea0;
					margin-top: 15px;
				}
			}
		}
	}
}

</style>
