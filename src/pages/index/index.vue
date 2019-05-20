<template>
  <div @click="clickHandle">
    <swiper
    :indicator-dots="indicatorDots"
    :autoplay="autoplay"
    :interval="interval"
    :duration="duration"
    >
  <block v-for="item in imgUrls" :key="item">
    <swiper-item>
      <image :src="item" class="slide-image" width="400" height="50" />
    </swiper-item>
  </block>
</swiper>
    <i-grid i-class="no-border">
    <i-grid-item i-class="no-border">
        <i-grid-icon>
            <image src="/static/grid/vip.png" />
        </i-grid-icon>
        <i-grid-label>会员</i-grid-label>
    </i-grid-item>
    <i-grid-item i-class="no-border">
        <i-grid-icon>
            <image src="/static/grid/电影.png" />
        </i-grid-icon>
        <i-grid-label>电影</i-grid-label>
    </i-grid-item>
    <i-grid-item i-class="no-border">
        <i-grid-icon>
            <image src="/static/grid/推荐.png" />
        </i-grid-icon>
        <i-grid-label>推荐</i-grid-label>
    </i-grid-item>
    <i-grid-item i-class="no-border">
        <i-grid-icon>
            <image src="/static/grid/最近.png" />
        </i-grid-icon>
        <i-grid-label>最近</i-grid-label>
    </i-grid-item>
</i-grid>
      <i-panel><view class="setting">
      <image src='/static/grid/反贪4.png' style="width:130rpx;height:180rpx;"></image>
      <text style="padding:7px;line-height:17px">
        <text class="movie">{{movie[0]}}</text>
        <text class="evaluate">\n{{evaluate[0]}}</text>
        <text class="actor">\n{{actor[0]}}</text> 
        <text class="play">\n{{play[0]}}</text> 
      </text>
      <button class="button">购票</button>
      </view></i-panel>
      <i-panel><view class="setting">
      <image src='/static/grid/复联4.png' style="width:130rpx;height:180rpx;"></image>
      <text style="padding:7px;line-height:17px">
        <text class="movie">{{movie[1]}}</text>
        <text class="evaluate">\n{{evaluate[1]}}</text>
        <text class="actor">\n{{actor[1]}}</text> 
        <text class="play">\n{{play[1]}}</text> 
      </text>
      <button class="button">购票</button>
      </view></i-panel>
      <i-panel><view class="setting" >
      <image src='/static/grid/调音师.png' style="width:130rpx;height:180rpx;"></image>
      <text style="padding:7px;line-height:17px">
        <text class="movie">{{movie[2]}}</text>
        <text class="evaluate">\n{{evaluate[2]}}</text>
        <text class="actor">\n{{actor[2]}}</text> 
        <text class="play">\n{{play[2]}}</text> 
      </text>
      <button class="button">购票</button>
      </view></i-panel>
      <i-panel><view class="setting">
      <image src='/static/grid/皮卡丘.png' style="width:130rpx;height:180rpx;"></image>
      <text style="padding:7px;line-height:17px">
        <text class="movie">{{movie[3]}}</text>
        <text class="evaluate">\n{{evaluate[3]}}</text>
        <text class="actor">\n{{actor[3]}}</text> 
        <text class="play">\n{{play[3]}}</text> 
      </text>
      <button class="button">购票</button>
      </view></i-panel>
      <i-panel><view class="setting">
      <image src='/static/grid/何以为家.png' style="width:130rpx;height:180rpx;"></image>
      <text style="padding:7px;line-height:17px">
        <text class="movie">{{movie[4]}}</text>
        <text class="evaluate">\n{{evaluate[4]}}</text>
        <text class="actor">\n{{actor[4]}}</text> 
        <text class="play">\n{{play[4]}}</text> 
      </text>
      <button class="button">购票</button>
      </view></i-panel>
      <i-panel><view class="setting">
      <image src='/static/grid/祈祷.jpg' style="width:130rpx;height:180rpx;"></image>
      <text style="padding:7px;line-height:17px">
        <text class="movie">{{movie[5]}}</text>
        <text class="evaluate">\n{{evaluate[5]}}</text>
        <text class="actor">\n{{actor[5]}}</text> 
        <text class="play">\n{{play[5]}}</text> 
      </text>
      <button class="button">购票</button>
      </view></i-panel>
      
  </div>
</template>

<script>
import card from '@/components/card'
export default {
  data : {
    movie:['反贪风暴4','复仇者联盟4:终局之战','调音师','大侦探皮卡丘','何以为家','祈祷落幕时'],
    evaluate: ['暂无评分','暂无评分','暂无评分','暂无评分','暂无评分','暂无评分'],
    actor: ['主演:古天乐，郑嘉颖，林峯',
    '主演:小罗伯特·唐尼、克里···',
    '主演:阿尤斯曼·库拉纳、塔···',
    '主演:贾斯提斯·史密斯、凯···',
    '主演:赞恩·阿尔·拉菲亚、Y···',
    '主演:阿部宽、松岛菜菜子···'],
    play: ['2019-04-04上映','2019-04-24上映','2019-04-03上映','2019-05-10上映','2019-04-29上映','2018-01-27上映'],
    imgUrls: [
      '/static/images/1.jpg',
      '/static/images/2.jpg',
      '/static/images/3.jpg'
    ],
    indicatorDots: false,
    autoplay: true,
    interval: 5000,
    duration: 1000
  },

  components: {
    card
  },

  methods: {
    
  }
}
</script>

<style scoped>
div >>> .no-border {
  border-width: 0pt;
}
.top-padding {
  padding-top: 20rpx;
}
.movie{
  color:black;
  font-size: 36rpx;
  font-family:microsoft yahei;
  font-weight:normal;
  letter-spacing:1.5px;
}
.evaluate{
  color:#696969;
  font-size:28rpx; 
  font-family:microsoft yahei;
  font-weight:normal;
}
.actor{
  color:#696969;
  font-size:28rpx;
  font-family:microsoft yahei; 
}
.play{
  color:rgb(148, 147, 147);
  font-size:28rpx;
  font-family:microsoft yahei;
}
.button{
  position: absolute;
  right: 12px;
  top: 32px;
  font-size:14px;
  background-color:#3bb3e0;
  color:white;
  margin:2.5px
}
.setting{
  display: flex;
  flex-direction: row;
  align-items: center;
  margin-left:9px;
  margin-top: 5px;
}

.userinfo {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.userinfo-avatar {
  width: 128rpx;
  height: 128rpx;
  margin: 20rpx;
  border-radius: 50%;
}

.userinfo-nickname {
  color: #aaa;
}

.usermotto {
  margin-top: 150px;
}

.form-control {
  display: block;
  padding: 0 12px;
  margin-bottom: 5px;
  border: 1px solid #ccc;
}
.all{
  width:7.5rem;
  height:1rem;
  background-color:blue;
}
.all:after{
  display:block;
  content:'';
  clear:both;
}
.left{
  float:left;
  width:3rem;
  height:1rem;
  background-color:red;
}

.right{
  float:left;
  width:4.5rem;
  height:1rem;
  background-color:green;
}
</style>
