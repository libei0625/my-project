<template>
  <div >
    <i-panel>
      <text>{{option.name}}</text>
      <button>{{option.name}}购票</button>
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
.home {
  display: inline-block;
  margin: 100px auto;
  padding: 5px 10px;
  color: blue;
  border: 1px solid blue;
}
</style>
