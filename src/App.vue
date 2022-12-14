<script >
import axios from "axios";
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import { store } from './components/store';
export default{
 name:"App",
  data() {
    return {
      store,
    }
  },
  methods:{
    getCharacter(){
      axios
      .get(store.apiUrl)
      .then(res =>{
        store.characterList = res.data.results;
      })
      .catch(err =>{
        console.log("Errori",err);
      }
      )
     
    }
   
  },
  components: {
    AppHeader,
    AppMain,
    
    
  },
  mounted() {
        this.getCharacter();
      }
}

</script>

<template>
  
<div id="container">
  <AppHeader  msg="Rick and Morty API"/>
  <AppMain/>
</div>
</template>


<style lang="scss">
@use'./components/styles/general.scss' as *;
@use'./components/styles/partials/variables.scss' as *;
#container{
  background-color: #2e3a46;
  width:100%;
 
  margin: 50px 0px auto;

}
</style>
