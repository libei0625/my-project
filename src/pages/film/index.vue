<template>
  <div >
    <view class="page">
  <view class="nav">
    <view :class="homeSelected?'current':'default'" @click="handleHomeSelected(e)">正在热映</view>
    <view :class="comingSelected?'current':'default'" @click="handleComingSelected(e)">即将上映</view>
  </view>
  <view :class="homeSelected?'show':'hidden'">
    <view class="nav-text">
      <i-panel v-for="item in recommand1" :key="item">
        <view class="setting">
          <image :src='item.img' style="width:130rpx;height:180rpx;"/>
          <text style="padding:7px;line-height:17px">
            <text class="movie">{{item.name}}</text>
            <text class="evaluate">\n{{item.evaluate}}</text>
            <text class="actor">\n演员:{{item.actor}}</text> 
            <text class="play">\n{{item.play}}上映</text> 
          </text>
        </view>
      </i-panel>
    </view>
  </view>

  <view :class="comingSelected?'show':'hidden'">
   <view class="nav-text">
     <i-panel v-for="item in recommand2" :key="item">
        <view class="setting">
          <image :src='item.img' style="width:130rpx;height:180rpx;"/>
          <text style="padding:7px;line-height:17px">
            <text class="movie">{{item.name}}</text>
            <text class="evaluate">\n{{item.evaluate}}</text>
            <text class="actor">\n演员:{{item.actor}}</text> 
            <text class="play">\n{{item.play}}上映</text> 
          </text>
        </view>
      </i-panel>
   </view>
  </view> 
</view>
  </div>
</template>

<script>
import now from '@/data/now.json'
import coming from '@/data/coming.json'
export default {
  data: {
    recommand1: now,
    recommand2: coming,
    homeSelected:true,
    comingSelected:false
  },
  methods: {
    
    handleHomeSelected(e){
        this.homeSelected = true
        this.comingSelected = false
    },
    handleComingSelected(e) {
      this.homeSelected = false
      this.comingSelected = true
    },
  },
  onLoad(option){
  }
}
</script>

<style scoped>
.nav{
  width:100%;
  height:80rpx;
  display:flex;
  position:fixed;
  top:0;
  left:0;
  background-color: #ffffff;
  z-index: 999;
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
.setting{
  display: flex;
  flex-direction: row;
  align-items: center;
  margin-left:9px;
  margin-top: 5px;
}
.default,.current{
  height:100%;
  line-height:80rpx;
  width:50%;
  text-align:center;
  border-bottom:1px solid #dfdfdf; 
}
.current{
   border-bottom:2px solid #000000;
}
.show{
  display:block;
}
.hidden{
  display:none;
}
.nav-text{
  margin-top:80rpx;
}
</style>
