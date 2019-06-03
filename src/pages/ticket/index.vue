<template>
  <div >
    <i-panel>
      <view class='header-container'>
        <image class='bg' :src='option.img'/>
        <view class='setting'>
          <image :src='option.img' style="width:250rpx;height:360rpx;"/>
          <text style="padding:8px;line-height:30px">
            <text class="movie">{{option.name}}</text>
            <text class="evaluate">\n{{option.evaluate}}</text>
            <text class="actor">\n演员:{{option.actor}}</text> 
            <text class="play">\n{{option.play}}上映</text> 
          </text>
        </view>
      </view>
    </i-panel>
    <button class="button" @click="jumpToAdd">购票</button>
    <i-panel style="margin-top:4px">
     <view class="li"  @click='changeToggle'>
        <view>剧情简介：</view>
        <image :src='hides[1]' style="margin-top:7px;height:25px;width:25px"></image>
     </view>
    <view :hidden="hides[0]">
      <block>
        <view class='introduce'>{{option.introduce}}</view>
      </block>
    </view>
    </i-panel>
  </div>
</template>

<script>

export default {
  methods: {
    changeToggle(){
    if (this.hides[0]==true && this.hides[1]=='/static/images/down.png'){
      this.hides=[false,'/static/images/up.png'];
    }else{
      this.hides=[true,'/static/images/down.png'];
    }

  },
    jumpToAdd(){
      wx.navigateTo({
        url:"../add/main"
      })
    }
  },
  data:{
    hides:[true,'/static/images/down.png'],
    option:[]
  },
  onLoad(option){
   this.option=option;
   console.log(option)
  }
}
</script>

<style>
.li {
  background-color: #fff;
  display: flex;
  justify-content: space-between;
  font-size: 34rpx;
  width: 92%;
  padding: 0 4%;
  height: 100rpx;
  line-height: 100rpx;
  border-bottom: 1rpx solid #f1f1f1;
}
.movie{
  color:white;
  font-size: 45rpx;
  font-family:microsoft yahei;
  font-weight:normal;
  letter-spacing:1.5px;
}
.evaluate{
  color:#D3D3D3;
  font-size:32rpx; 
  font-weight:normal;
}
.actor{
  color:#D3D3D3;
  font-size:32rpx;
  font-family:microsoft yahei; 
}
.play{
  color:#D3D3D3;
  font-size:32rpx;
  font-family:microsoft yahei;
}
.setting{
  width: 750rpx;
  height: 450rpx;
  color: rgb(213, 214, 210);
  position: absolute;
  display: flex;
  flex-direction: row;
  align-items: center;
  margin-left: 15px;
}
.header-container {
  display: flex;
  flex-direction: row;
  height: 450rpx;
  background-color: #fff;
  align-items: center;
  position: relative; 
}
.bg{
filter: blur(9px);
width: 100%;
height: 100%;
}
.button{
  font-size: 20px;
  background-color:#3bb3e0;
  height:50px;
  width: 100%
}
.introduce{
  font-size: 35rpx;
  color:#696969;
  margin-left: 20px;
  margin-right: 20px
}
</style>
