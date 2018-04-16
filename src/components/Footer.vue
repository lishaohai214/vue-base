<template>
  <div class="v-footer">
      <p>{{ title }} - {{ copyright }}</p>
  </div>
</template>

<script>

export default {
  name: 'v-footer',
  props:{
  	title:{
  		type: String,
  		require:true
  	}
  },
  data () {
    return {
    	copyright:"2018 demo "
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .v-footer{
  	background-color: #222;
  	padding: 10px;
  }
  p{
  	color: green;
  	text-align: center;
  }
</style>
