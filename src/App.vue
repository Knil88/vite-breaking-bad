<script >
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';

export default{
  components: {
    AppHeader,
    AppMain,
    
  }
}

</script>

<template>
  
<div id="container">
  <AppHeader/>
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
