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
	</view>
</template>

<script>
	import Navbar from '@/components/navbar/navbar.vue'
	export default {
		data() {
			return {
				topBanner: []
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
			Navbar
		}
	}
</script>

<style lang="scss">
.home{
	display: flex;
	flex-direction: column;
	flex: 1;
	
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
}
</style>
