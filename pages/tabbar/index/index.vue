<template>
	<view class="home">
		<Navbar />
		
		<view class="index_banner_box">
			<swiper :indicator-dots="true" :autoplay="true" :interval="3000" :duration="500">
				<swiper-item class="swiper" v-for="(item, index) in topBanner" :key="index">
					<image class="banner" :src="item.urls.regular" mode="aspectFill"></image>
				</swiper-item>
			</swiper>
		</view>
		
		<courseNav />
		
		<view class="online_box" v-if="index_banner.length > 1" >
			<image :src="index_banner[1].urls.regular"></image>
		</view>
		
		<view class="free_box">
			<view class="free_T_box public_tow_box">
				<view class="public_T">
					限时免费
				</view>
			</view>
		</view>
		
		<FreeCard />
	</view>
</template>

<script>
	import Navbar from '@/components/navbar/navbar.vue'
	import courseNav from '@/components/courseNav/courseNav.vue'
	import FreeCard from '@/components/free-card/free-card.vue'
	export default {
		data() {
			return {
				topBanner: [],
				index_banner: [],
			}
		},
		methods: {
			
		},
		mounted() {
			// Request multiple photos (e.g., 5) for the banner
			uni.request({
				url: "https://api.unsplash.com/photos/random?count=5&query=tech&client_id=oFWnfAJEQYjgmZiCVVSpiLH3n1Kz4NJWRLxhzaaTMw4",
				// 注意
				success: (res) => {
					console.log('API response:', res.data); // Debug log
					this.topBanner = res.data;
					this.index_banner = res.data;
				},
				fail: (err) => {
					console.log('API request fail');
				}
				// success(res){
				// 	console.log(res.data)
				// }
			})
		},
		components: {
			Navbar,
			courseNav,
			FreeCard
		}
	}
</script>

<style lang="scss">
.home{
	display: flex;
	flex-direction: column;
	flex: 1;
	overflow: hidden;
	
	.index_banner_box {
		width: 100%;
		padding: 10rpx;
		justify-content: center;
		align-items: center;
		border-radius: 5px;
		box-sizing: border-box;
		overflow: hidden;
		
		.swiper{
			width: 100%;
			height: 300rpx;
			
			.banner {
				width: 100%;
				height: 100%;
			}
		}
	}
	.online_box{
		display: flex;
		width: 750rpx;
		justify-content: center;
		align-items: center;
		box-sizing: border-box;
		overflow: hidden;
		margin-bottom: 15px;
		
		.online_img{
			width: 724rpx;
			height: 132rpx;
		}
	}
	.public_tow_box {
		display: flex;
		width: 100%;
		justify-content: center;
		align-items: center;
		box-sizing: border-box;
		overflow: hidden;
		padding: 0 15px;
		justify-content: space-between;
		align-content: space-between;
		flex-wrap: wrap;
		
		.public_T{
			font-size: 20px;
			font-weight: 700;
		}
	}
}
</style>
