<template>
	<view>
		
		<view class="uni-tab-bar">
			<scroll-view scroll-x class="uni-swiper-tab">
				<block v-for="(tab,index) in tabBars" :key="tab.id">
					<view 
						class="swiper-tab-list" 
						:class="{'active':tabIndex == index}"
						@click="tabClick(index)"
					>
						{{tab.name}}
						<view class="tab-list-line"></view>
					</view>
				</block>
			</scroll-view>
		</view>
		
		<view class="uni-tab-bar">
			<swiper 
				class="swiper-box" 
				:style="{'height':swiperHeight+'px'}"
				:current="tabIndex"
				@change="tabChange"
			>
				<swiper-item v-for="(items,indexs) in newsList" :key="indexs">
					<scroll-view scroll-y class="list">
						<block v-for="(item,index) in items.list" :key="index">
							<index-list :item="item" :index="index"></index-list>
						</block>
					</scroll-view>
				</swiper-item>
			</swiper>
		</view>
		
		
		<!-- <block v-for="(item,index) in list" :key="index">
			<index-list :item="item" :index="index"></index-list>
		</block> -->
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
				swiperHeight:573,
				tabIndex:0,
				tabBars:[
					{name:'关注',id:'guanzhu'},
					{name:'推荐',id:'tuijian'},
					{name:'体育',id:'tiyu'},
					{name:'热点',id:'redian'},
					{name:'财经',id:'caijing'},
					{name:'娱乐',id:'yule '}
				],
				newsList:[
					{
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
					},
					{
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
							},
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
					},
					{
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
							},
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
							},
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
					},
					{
						list:[]
					},
					{
						list:[]
					},
					{
						list:[]
					}
				]
			}
		},
		onLoad(){
			uni.getSystemInfo({
			    success:(res)=>{//es5语法不生效
			        console.log(res.windowHeight);
					let height = res.windowHeight-uni.upx2px(100)
					this.swiperHeight = height
			    }
			});
		},
		methods: {
			tabClick(index){//顶部tabBar点击事件
				this.tabIndex = index
			},
			tabChange(e){//滑动切换页面
				this.tabIndex = e.detail.current
			}
		}
	}
</script>

<style>
	.uni-swiper-tab{
		border-bottom: 1upx solid #eee;
	}
	.swiper-tab-list{
		color: #969696;
		font-weight: bold;
	}
	.uni-swiper-tab .active{
		color: #343434;
	}
	.active .tab-list-line{
		border-bottom: 6upx solid #fede33;
		width: 70upx;
		margin: auto;
		border-top: 6upx solid #fede33;
		border-radius: 20upx;
	}
</style>
