<template>
	<view>
		<view class="box-bg">
			<uni-nav-bar shadow statusBar :fixed="false" color="#333333" background-color="#ffffff" right-icon="scan">
				<view class="input-view">
					<uni-icons class="input-uni-icon" type="search" size="18" color="#999" />
					<input confirm-type="search" class="nav-bar-input" type="text" placeholder="输入搜索关键词"/>
				</view>
			</uni-nav-bar>
		</view>
	</view>
</template>

<script>
	import uniNavBar from '@/components/uni-nav-bar/uni-nav-bar.vue'
	export default {
		data() {
			return {
				
			}
		},
		methods: {
			
		},
		components: {
			uniNavBar
		}
	}
</script>

<style lang="scss">
	$nav-height: 30px;
	.box-bg {
		background-color: #F5F5F5;
		padding: 5px 0;
	}

	.input-view {
		/* #ifndef APP-PLUS-NVUE */
		display: flex;
		/* #endif */
		flex-direction: row;
		width: 60px;
		flex: 1;
		background-color: #f8f8f8;
		height: $nav-height;
		border-radius: 15px;
		padding: 0 15px;
		flex-wrap: nowrap;
		margin: 7px 0;
		line-height: $nav-height;
	}

	.input-uni-icon {
		line-height: $nav-height;
	}

	.nav-bar-input {
		height: $nav-height;
		line-height: $nav-height;
		/* #ifdef APP-PLUS-NVUE */
		width: 370rpx;
		/* #endif */
		padding: 0 5px;
		font-size: 12px;
		background-color: #f8f8f8;
	}
</style>
