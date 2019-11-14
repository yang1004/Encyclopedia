<template>
	<view>
		<block v-for="(item,index) in list" :key="index">
			<index-list :item="item" :index="index"></index-list>
		</block>
	</view>
</template>

<script>
	import indexList from "../../components/index/index-list.vue"
	export default {
		components:{
			indexList
		},
		data() {
			return {
				list:[
					{
						userpic:'../../static/demo/userpic/12.jpg',//用户头像
						username:'昵称',//用户名
						isFollow:false,//是否关注 true:未关注 false：已关注
						titlle:'我是标题',//标题
						type:'img', //img为图文 video为视频
						titlepic:'../../static/demo/datapic/11.jpg',
						infoNum:{
							index:1, //0:没操作 1:顶 2:踩
							dingNum:11,
							caiNum:10
						},
						commentNum:11,//评论
						shareNum:10,//分享
					},
					{
						userpic:'../../static/demo/userpic/12.jpg',//用户头像
						username:'昵称',//用户名
						isFollow:true,//是否关注
						titlle:'我是标题',//标题
						type:'img', //img为图文 video为视频
						titlepic:'../../static/demo/datapic/11.jpg',
						playNum:"20w",
						long:"2:47",
						infoNum:{
							index:2, //0:没操作 1:顶 2:踩
							dingNum:11,
							caiNum:10
						},
						commentNum:11,//评论
						shareNum:10,//分享
					}
				]
			}
		},
		methods: {
			
		}
	}
</script>

<style>
	
</style>
