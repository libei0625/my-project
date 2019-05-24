<template>
  <div>

    <swiper
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
      <i-grid-item @click="goToJump(item.url)" v-for="item in grid" :key="item" i-class="no-border">
        <i-grid-icon><image :src="item.img" /></i-grid-icon>
        <i-grid-label>{{item.name}}</i-grid-label>
      </i-grid-item>
    </i-grid>

    <i-panel v-for="item in recommand" :key="item">
      <view class="setting">
        <image :src='item.img' style="width:130rpx;height:180rpx;"/>
        <text style="padding:7px;line-height:17px">
          <text class="movie">{{item.name}}</text>
          <text class="evaluate">\n{{item.evaluate}}</text>
          <text class="actor">\n演员:{{item.actor}}</text> 
          <text class="play">\n{{item.play}}上映</text> 
        </text>
        <button class="button" @click='jump(item)'>购票</button>
      </view>
    </i-panel>

  </div>
</template>

<script>
import card from '@/components/card'
import top from '@/data/top.json'
export default {
  data : {
    grid:[
      {type:"1","name":"会员","img":"/static/grid/会员.png","url":"../vip/main"},
      {type:"2","name":"电影","img":"/static/grid/电影.png","url":"../ticket/main"},
      {type:"3","name":"推荐","img":"/static/grid/推荐.png","url":"../ticket/main"},
      {type:"4","name":"最近","img":"/static/grid/最近.png","url":"../ticket/main"}
    ],
    imgUrls: [
      '/static/images/1.jpg',
      '/static/images/2.jpg',
      '/static/images/3.jpg'
    ],
    indicatorDots: false,
    autoplay: true,
    interval: 5000,
    duration: 1000,
    recommand:top
  },

  components: {
    card
  },

  methods: {
    goToJump(url){
      wx.navigateTo({url})
    },
    jump(item){
    wx.navigateTo({
       url:'../ticket/main?id='+item.id+'&name='+item.name+'&evaluate='+item.evaluate+
       '&actor='+item.actor
    })
    }
  }
}
</script>
<style scoped>
div >>> .no-border {
  border-width: 0pt;
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
