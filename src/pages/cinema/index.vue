<template>
<div style="width: 100%; height: 100%;">
  <map
  id="map"
  longitude="113.324520"
  latitude="23.099994"
  scale="14"
  :controls="controls"
  @controltap="controltap"
  :markers="markers"
  @markertap="markertap"
  :polyline="polyline"
  @regionchange="regionchange"
  show-location
  style="width: 100%; height: 300px;"
></map>
</div>
</template>

<script>
import card from '@/components/card'

export default {
  data () {
    return {
    markers: [{
      iconPath: '/resources/others.png',
      id: 0,
      latitude: 23.099994,
      longitude: 113.324520,
      width: 50,
      height: 50
    }],
    polyline: [{
      points: [{
        longitude: 113.3245211,
        latitude: 23.10229
      }, {
        longitude: 113.324520,
        latitude: 23.21229
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
body,html{height:100%}
</style>
