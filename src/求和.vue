<template>
  <div>
<span v-for="(obj,index) in arr" :key="index"><input type="checkbox" v-model="list" :value="obj">{{obj}}</span>

<p>你选中得元素，累计得值和为：{{sum}}</p>
  </div>
</template>

<script>
export default {
  data () {
    return {
      list:[],
arr:[9, 15, 19, 25, 29, 31, 48, 57, 62, 79, 87]
    }
  },

  computed: {
sum(){
return this.list.reduce((num,obj)=>{
  return num+=obj
},0)
}
  },

 
}
</script>

<style scoped>

</style>
