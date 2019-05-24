<template>
  <div >
    <i-panel>
      <text>{{name}}</text>
      <button>{{name}}购票</button>
    </i-panel>
  </div>
</template>

<script>

export default {
  methods: {
  },
  Data(){
    
  },
  onLoad(option){
    console.log(option.name)
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
