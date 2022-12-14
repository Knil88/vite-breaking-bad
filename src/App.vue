<script >
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
  components: {
    AppHeader,
    AppMain,
    
  }
}

</script>

<template>
  
<div id="container">
  <AppHeader  msg="Rick and Morty"/>
  <AppMain/>
</div>
</template>


<style lang="scss">
@use'./components/styles/general.scss' as *;
@use'./components/styles/partials/variables.scss' as *;
#container{
  background-color: #2e3a46;
  width: 100%;
 height: 500px;
  margin: 50px 0px auto;

}
</style>
