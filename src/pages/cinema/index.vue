<template>
<div style="width: 100%; height: 100%;">
  <map
  id="map"
  longitude="114.340713"
  latitude="30.58292"
  scale="14"
  :controls="controls"
  @controltap="controltap"
  :markers="markers"
  @markertap="markertap"
  :polyline="polyline"
  @regionchange="regionchange"
  show-location
  style="width: 100%; height: 100%;"
  enable-zoom="false"
  show-compass="true"></map>
</div>
</template>

<script>
import card from '@/components/card'

export default {
  data () {
    return {
    markers: [{
      iconPath: '/static/images/定位.png',
      id: 0,
      latitude: 30.58292,
      longitude: 114.340713,
      width: 50,
      height: 50
    }],
    polyline: [{
      points: [{
        longitude: 114.340713,
        latitude: 30.58292
      }, {
        longitude: 114.340713,
        latitude: 30.58292
      }],
      color: '#FF0000DD',
      width: 2,
      dottedLine: true
    }],
    controls: []
    }
  },

  components: {
    card
  },

  methods: {
  regionchange(e) {
    console.log(e.type)
  },
  markertap(e) {
    console.log(e.markerId)
  },
  controltap(e) {
    console.log(e.controlId)
  }
  },

  created () {
    // let app = getApp()
  }
}
</script>

<style>
body,html{height: 100%}
</style>
