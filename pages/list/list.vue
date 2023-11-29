<template>
	<view class="list">
		<musichead title="歌单漫游" :icon="true" color="black"></musichead>
	<view class="list">
	  <view v-for="(item, index) in playList" :key="index" style="padding: 12px 0; border-bottom: 3px solid #ccc;">
	    <view class="index-list-item" style="display: flex; align-items: center; position: relative;">
	      <text style="flex: 1; margin-left: 5%;">{{ item.name }}</text>  {{item.ar.name}}
	      <view style="position: relative; width: 50px; height: 50px; margin-right: 5%;">
	        <image :src="item.al.picUrl" mode="" style="width: 100%; height: 100%; border-radius: 50%;"></image>
	        <text class="iconfont iconbofang" style="position: absolute; top: 50%; left: 50%; transform: translate(-50%, -50%); font-size: 24px;" @tap="handleToDetail(item.id)"></text>
	      </view>
	    </view>
	  </view>
	</view>


	</view>
</template>

<script>
	import musichead from '../../components/musichead/musichead.vue'
	import '@/common/iconfont.css'
	import { list } from '../../common/api.js'
	export default {
		data() {
			return {
                playList : [],
			}
		},
		components : {
			musichead
		},
		onLoad(options){
             list(options.listId).then((res)=>{
				console.log(res[1].data.songs);
				this.playList = res[1].data.songs;
			 });
		},
		methods: {
		     handleToDetail(songId){
		     	uni.navigateTo({
		     		url: '/pages/detail/detail?songId=' + songId
		     	});
		     },
		}
	}
</script>

<style scoped>

</style>
