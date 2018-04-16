<template>
  <div class="v-header" v-on:click="changeTitle">
      <h1>{{ title }}</h1>
  </div>
</template>

<script>



export default {
  name: 'v-header',
  props:{  
  	title:{
  		type:String,
      require:true
  	}	
  },
  data () {
    return {
    	// title:"Vue.js Demo"
    }
  },
  methods:{
  	changeTitle(){
  		// this.title = "changed"
  		// alert('dadf')

  		this.$emit("changedTitle","子组件向父组件赋值")
  	}
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .v-header{
    background-color: #222;
    padding: 10px;
  }
  h1{
    text-align: center;
    color: green;
  }
</style>
