<template>
  <div >
    <i-panel hide-border='true' style="margin:2px;">
      <view style="width:100%; display:flex;">
        <view>用户名：</view>
        <input style="border: 1px solid;border-color: black;width:70%;"
         maxlength="16" type="text" focus="false"/>
      </view>
    </i-panel>
    <i-panel hide-border='true' style="margin:2px;">
      <view style="width:100%; display:flex;">
        <view>票　数：</view>
        <input style="border: 1px solid;border-color: black;width:70%;"
          maxlength="16" type="text" focus="false"/>
      </view>
    </i-panel>
  </div>
</template>

<script>
// Use Vuex


export default {
  methods:{

  }
}
</script>

<style>
.setting{
  position:relative;
}

</style>
