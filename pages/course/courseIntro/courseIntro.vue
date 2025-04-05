<template>
	<view>
		课程介绍
	</view>
</template>

<script>
	export default {
		data() {
			return {
				introduce: {}
			}
		},
		methods: {
			
		},
		onLoad(options){
			console.log(options)
			uni.request({
				url: "DONT HAVE ACCESS",
				data: {
					id: options.id,
					course: options.course
				},
				success(res) {
					this.introduce = res.data;
				}
			})
		}
	}
</script>

<style>

</style>
