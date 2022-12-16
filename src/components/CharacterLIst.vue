<script >

// Importiamo il file SingleCharacter 

import SingleCharacter from "./SingleCharacter.vue"

import {store} from './store'
   export default{
        name:"CharacterList",
        components:{
            SingleCharacter,
        },
        data() {
            return {
                store,
            }
        },
   }
</script>

<template>
  
   
        <section id="card-container">
          
            
           <div id="count">
              <p> WE HAVE FOUND  {{store.characterList.length}} CHARACTERS </p>
           </div>
               
            <div class="big-card" v-for="character in store.characterList" 
            :key="character.id">
            <SingleCharacter :info="character"/>
            </div>
      
        </section>
 
</template>

<style lang="scss" scoped>
#status{
    margin: 8px auto;
    padding: 5px;
    font-size: 13px;
}
    #card-container{
        display: flex;
        justify-content:center;
        flex-wrap: wrap;
        margin: auto;
        width:100%;
        background: rgb(2,0,36);
        background: linear-gradient(90deg, rgba(2,0,36,1) 0%, rgba(175,180,28,1) 24%, rgba(148,198,123,0.9261904590937937) 69%, rgba(0,212,255,1) 100%);
         

        .big-card{
            text-align: center;
            margin: 13px;
          
          
            
        }

    }
    #count{
        background-color: aliceblue;
        width: 95%;
        padding: 10px;
        color: blue;
        margin: 10px;
        font-weight: bolder;
    }
</style>
