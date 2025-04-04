<template>
	<view class="course_nav">
		<view class="course_nav_info" v-for="(item, index) in list" :key="index">
			<!-- v-bind: 简写: -->
			<text class="course_nav_icon icon iconfont" :class="item.icon"></text>
			<view class="course_info_text">{{ item.text }}</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return{
				list: []
			}
		},
		mounted(){
			this.list = require('@/common/data.json');
			//console.log(this.list)
		}
	}
</script>

<style lang="scss">
	@import "@/common/icofont/icofont/icofont.css";
	.course_nav{
		display: flex;
		// 盒子模型不撑开容器本身大小
		box-sizing: border-box;
		flex-direction: row;
		flex-wrap: wrap;
		// 上下 左右
		padding: 15px 10px;
		
		.course_nav_info{
			width: 20%;
			flex-direction: row;
			flex-wrap: wrap;
			text-align: center;
			margin-bottom: 15px;
			
			.course_nav_icon {
				font-size: 30px;
			}
			.icofont-brand-java {
				color: #2a83fe;
			}
			.icofont-file-python {
				color: #fd6012;
			}
			.icofont-web {
				color: #00b478;
			}
			.icofont-data{
				color: #2b91e2;
			}
			.course_info_text {
				width: 100%;
				font-size: 13px;
				margin-top: 10px;
				white-space: nowrap;
				text-overflow: ellipsis;
				overflow: hidden;
			}
		}
	}
</style>