<script >



import {store} from './store'
   export default{
        name:"Appsearch",
      
        data() {
            return {
                store,
            }
        },
   }
</script>

<template>
  
    <section>
        <select name="Status" id="status" @click="$emit('search')" v-model="store.searchText"  placeholder="Select Category">
           
            <option value="alive" >
                Alive
            </option>
            <option value="unknown" >
              Unknown
            </option>
            <option value="dead" >
               Dead
            </option>
           
        </select>
    </section>
      
 
</template>

<style lang="scss" scoped>
#status{
    margin: 8px auto;
    padding: 5px;
    font-size: 13px;
}
   
        

      

    
  
</style>
