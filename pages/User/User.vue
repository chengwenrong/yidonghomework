<template>
	<view>
		<musichead title="近期演唱会最新消息" :icon="false" color="white"></musichead>
	
			<swiper :indicator-dots="true" :autoplay="true" interval="3000" duration="500" class="container">
				<block v-for="(item,index) in imgList" :key="index">
					<swiper-item class="centered-image">
						<image :src="item"></image>
					</swiper-item> 
					
				</block>
			</swiper>  

	</view>
</template>

<script>
	import musichead from '../../components/musichead/musichead.vue'
	export default {
		data() {
			return {
				musichead,
				imgList:[
							"https://pic.rmb.bdstatic.com/dc9f555a223a701d1e17511090d6156a.jpeg",
							"https://i2.sinaimg.cn/ent/y/p/2009-06-28/U105P28T3D2586203F346DT20090628124332.jpg",
							"https://inews.gtimg.com/newsapp_bt/0/11336947529/1000"
					    ],
			}
		},
		methods: {
			
		}
	}
</script>

<style scoped>
 .container {
	 margin-top: 5%;
     display: flex;
     justify-content: center; /* 水平居中 */
     align-items: center; /* 垂直居中 */
     height: 180px; /* 视口的高度 */
   }
   
   .centered-image {
  max-width: 100%; /* 图片最大宽度为容器宽度 */
   margin-left: 8%;
   }
   
   .container-content{
	   margin-top: 10%;
	   justify-content: center;
	   align-items: center;
	   color: forestgreen;
	   margin-left: 5%;
	   font-weight: 900;
   }
</style>
