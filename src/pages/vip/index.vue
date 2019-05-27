<template>
  <div >
    <i-panel>
      <view class="header-container">
        <image class='header-bg' src = '/static/images/背景.jpg'/>
        <view class="userinfo">
          <view class="userinfo-avatar">
            <open-data type="userAvatarUrl"></open-data>
          </view>
          <view class="right">
            <open-data type="userNickName"></open-data>
            <view class="below">
              <image class='font1' src='/static/images/星星.png'/>
              <image class='font1' src='/static/images/星星.png'/>
              <image class='font1' src='/static/images/星星.png'/>
              <image class='font2' src='/static/images/月亮.png'/>
              <image class='font2' src='/static/images/月亮.png'/>
            </view>
          </view>
        </view>
      </view>
    </i-panel>
      <i-grid i-class="no-border">
        <i-grid-item i-class="no-border" v-for="item in gridsOne" :key="item">
          <i-grid-icon>
              <image class='image' :src="item.img" />
          </i-grid-icon>
          <i-grid-label>{{item.type}}</i-grid-label>
        </i-grid-item>
      </i-grid>
      <i-grid i-class="no-border">
        <i-grid-item i-class="no-border" v-for="item in gridsTwo" :key="item">
          <i-grid-icon>
              <image class='image' :src="item.img" />
          </i-grid-icon>
          <i-grid-label>{{item.type}}</i-grid-label>
        </i-grid-item>
      </i-grid>
      <i-grid i-class="no-border">
        <i-grid-item i-class="no-border" v-for="item in gridsThree" :key="item">
          <i-grid-icon>
              <image class='image' :src="item.img" />
          </i-grid-icon>
          <i-grid-label>{{item.type}}</i-grid-label>
        </i-grid-item>
    </i-grid>
  </div>
</template>

<script>
// Use Vuex
export default {
  methods: {
  },
  data(){
    return{
      gridsOne: [
        {type:'新片首发',img:'/static/images/新品.png'},
        {type:'独家影片',img:'/static/images/独家.png'}
        ],
      gridsTwo: [
        {type:'画质高清',img:'/static/images/hd.png'},
        {type:'服务更好',img:'/static/images/点赞.png'}
      ],
      gridsThree: [
      {type:'无广告',img:'/static/images/无广告.png'},
        {type:'会员加速',img:'/static/images/加速.png'}
      ],
    }
  },
  onLoad(option){
  }
}
</script>

<style scoped>
.no-border {
  border-width: 0pt;
}
.image{
  width:80rpx;
  height:80rpx;
}
.header-container {
  display: flex;
  flex-direction: row;
  height: 200rpx;
  background-color: #fff;
  align-items: center;
  position: relative;
  
}
.bg{
width: 100%;
height: 100%;
}
.split {
  margin-bottom: 10pt;
}
.userinfo {
width: 750rpx;
height: 320rpx;
color: rgb(213, 214, 210);
position: absolute;
display: flex;
flex-direction: row;
align-items: center;
}
.right{
display: flex;
flex-direction: column; 
align-items: left;
}
.below{
display: flex;
flex-direction: row; 
align-items: center; 
}
.userinfo-avatar {
overflow:hidden;
width: 120rpx;
height: 120rpx;
margin: 20rpx;
margin-top: 10rpx;
border-radius: 50%;
border: 2px solid #BEBEBE;
box-shadow: 3px 3px 10px rgba(0, 0, 0, 0.2);
}
.font1{
  width:40rpx;
  height:40rpx;
}
.font2{
  width:35rpx;
  height:35rpx;
}
.home {
  display: inline-block;
  margin: 100px auto;
  padding: 5px 10px;
  color: blue;
  border: 1px solid blue;
}
</style>
