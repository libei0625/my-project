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
    <button class="button">购票</button>
    <i-panel style="margin-top:4px">
    <view>剧情简介：</view>
    <view class='introduce'>
      <text>{{option.introduce}}</text>
    </view>
    </i-panel>
  </div>
</template>

<script>

export default {
  methods: {
  },
  data(){
   return{
      option:[]
   }
  },
  onLoad(option){
   this.option=option;
   console.log(option)
  }
}
</script>

<style>
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
  background-color:#3bb3e0;
}
.introduce{
  font-size: 35rpx;
  color:#696969;
  margin-left: 20px;
  margin-right: 20px
}
</style>
