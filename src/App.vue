<template >
  <div id="App">
    <hookPart></hookPart>
   </div>
</template>

<script>
import hookPart from './components/hook'

export default {
  name: 'App',
  data(){
    return{
      
    }
  },
  components:{
    hookPart
  },
  
  
 
}
</script>

<style>
#App{
  text-align: center;
  margin-top:29px
}

</style>
