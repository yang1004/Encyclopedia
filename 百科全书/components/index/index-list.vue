<template>
	<view class="index-list">
		<view class="index-list1 u-f-ac u-f-jsb">
			<view class="u-f-ac">
				<image :src="item.userpic" mode="widthFix" lazy-load></image>
				{{item.username}}
			</view>
			<view class="u-f-ac" v-show="item.isFollow">
				<!-- v-if会导致元素未渲染 css样式乱 -->
				<view class="icon iconfont icon-zengjia"></view>
				关注
			</view>
		</view>
		<view class="index-list2">我是标题</view>
		<view class="index-list3 u-f-ajc">
			<!-- 图片 -->
			<image :src="item.titlepic" mode="widthFix" lazy-load></image>
			<!-- 视频 -->
			<template v-if="item.type == 'video'">
				<view class="icon iconfont icon-bofang index-list-play"></view>
				<view class="index-list-playInfo">
					{{item.playNum}}次播放 {{item.long}}
				</view>
			</template>
			
		</view>
		<view class="index-list4 u-f-ac u-f-jsb">
			<view class="u-f-ac">
				<view class="u-f-ac" :class="{'active':item.infoNum.index == 1}">
					<view class="icon iconfont icon-icon_xiaolian-mian"></view>
					{{item.infoNum.dingNum}}
				</view>
				<view class="u-f-ac" :class="{'active':item.infoNum.index == 2}">
					<view class="icon iconfont icon-kulian"></view>
					{{item.infoNum.caiNum}}
				</view>
			</view>
			<view class="u-f-ac">
				<view class="u-f-ac"><view class="icon iconfont icon-pinglun1"></view>{{item.commentNum}}</view>
				<view class="u-f-ac"><view class="icon iconfont icon-zhuanfa"></view>{{item.shareNum}}</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		props:{
			item:Object,
			index:Number
		}
	}
</script>

<style>
	.index-list{
		padding: 20upx;
		border-bottom: 1upx solid #eee;
	}
	.index-list1>view:first-child{
		color: #929292 ;
	}
	.index-list1>view:first-child image{
		width: 85upx;
		height: 85upx;
		border-radius: 100%;
		margin-right: 10upx;
	}
	.index-list1>view:last-child{
		background-color: #f4f4f4;
		border-radius: 5upx;
		padding: 0 10upx;
	}
	.index-list2{
		padding-top: 15upx;
		font-size: 32upx;
	}
	.index-list3{
		position: relative;
		padding-top: 15upx;
	}
	.index-list3>image{
		width: 100%;
		border-radius: 20upx;
	}
	.index-list4{
		padding: 15upx 0;
	}
	.index-list4 view{
		color: #999;
	}
	.index-list4>view>view>view{
		/* 底部图标样式 */
		margin-right: 10upx;
	}
	.index-list4>view>view:first-child{
		/* 底部左右图标第一个样式 */
		margin-right: 10upx;
	}
	.index-list-play{
		position: absolute;
		font-size: 140upx;
		color: #fff;
	}
	.index-list-playInfo{
		position: absolute;
		background-color: rgba(51,51,51,0.72);
		color: #fff;
		bottom: 8upx;
		right: 8upx;
		border-radius: 40upx;
		font-size: 22upx;
		padding: 0 12upx;
	}
	.index-list4 .active,.index-list4 .active>view{
		color: #c5f61c;
	}
</style>
