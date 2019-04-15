<template>
  <div @click="clickHandle">
    <i-notice-bar icon="systemprompt" loop color="#EE2C2C">
    湖大电影院上线啦！！！
    </i-notice-bar>
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
    <i-panel i-class="top-padding" >
      <view class="top-padding"></view>
      <i-card title="反贪风暴4" i-class="top-padding" extra="额外内容" thumb="/static/grid/fan.png">
        <view slot="content">主演：古天乐，郑嘉颖，林峯</view>
        <view slot="footer">暂无评分</view>
      </i-card>
      <view class="top-padding"></view>
      <i-card title="卡片标题" i-class="top-padding" extra="额外内容" thumb="/static/grid/调音师.jpg">
        <view slot="content">内容不错</view>
        <view slot="footer">尾部内容</view>
      </i-card>
      <view class="top-padding"></view>
      <i-card title="卡片标题" i-class="top-padding" extra="额外内容" thumb="https://i.loli.net/2017/08/21/599a521472424.jpg">
        <view slot="content">内容不错</view>
        <view slot="footer">尾部内容</view>
      </i-card>
      <view class="top-padding"></view>
      <i-card title="卡片标题" i-class="top-padding" extra="额外内容" thumb="https://i.loli.net/2017/08/21/599a521472424.jpg">
        <view slot="content">内容不错</view>
        <view slot="footer">尾部内容</view>
      </i-card>
    </i-panel>
  </div>
</template>

<script>
import card from '@/components/card'
export default {
  data : {
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
    bindViewTap () {
      const url = '../logs/main'
      if (mpvuePlatform === 'wx') {
        mpvue.switchTab({ url })
      } else {
        mpvue.navigateTo({ url })
      }
    },
    clickHandle (ev) {
      console.log('clickHandle:', ev)
      // throw {message: 'custom test'}
    }
  },

  created () {
    // let app = getApp()
  }
}
</script>

<style scoped>
div >>> .no-border {
  border-width: 0pt;
}
.top-padding {
  padding-top: 50rpx;
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
