<!-- Andiamo ad importare i vari components ed azios che ci servirà ad agganciare la API -->

<script >
import axios from "axios";
import AppHeader from './components/AppHeader.vue';
import CharacterList from './components/CharacterList.vue';
import AppSearch from './components/AppSearch.vue';
import { store } from './components/store';

// creiamo l'export default e nei data mettiamo return store cosi da poterlo richiamare in APP.vue

export default{
 name:"App",
  data() {
    return {
      store,
    }
  },

// Creiamo il metodo per richiamre la nostra characterList

  methods:{
    getCharacter(){
    
      // Creiamo la variabile myUrl che richiama store.apiUrl
      
      let myUrl = this.store.apiUrl

      //Poniamo la condizione che se searchText è diverso  da stringa vuota aggiungiamo ad myUrl lo status che richiam il valore di store.searchText

      if(this.store.searchText != ""){
           myUrl += `?status=${this.store.searchText} `
        }
      axios
      
      //con questo methods richiamiamo myUrl
      .get(myUrl)
      
      //Con then diciamo che tutto è andato per il verso giusto 
      .then(res =>{

        //quando definiamo con methods dobbiamo ricordarci sempre di aggiungere this.nomevariabile

        this.store.characterList = res.data.results;
      })

      //Con catch diciamo che ci sono stati degli errori 

      .catch(err =>{
        console.log("Errori",err);
      }
      )
     
    }
   
  },
  //mettiamo tutti i file importati in components

  components: {
    AppHeader,
    CharacterList ,
    AppSearch,
    
    
  },

  //con mounted andiamo a definire la nostra funzione in modo che possa avviarsi

  mounted() {
        this.getCharacter();
      }
}

</script>

<template>
  
<div id="container">
  <AppHeader msg="Rick and Morty API"/>
  <main>

    <!-- agganciamo @search con AppSearch da poter richiamare $emit -->

    <AppSearch @search="getCharacter()"/>
    <CharacterList  />
  </main>
 
</div>
</template>

<!-- Agganciamo con use tutti i file contenuti nella cartella styles cosi da poterli utilizzare    -->

<style lang="scss">

 @use'./components/styles/general.scss' as *;
@use'./components/styles/partials/variables.scss' as *;
#container{
  background-color: #2e3a46;
  width:100%;
 
  margin: 50px 0px auto;

}
</style>
