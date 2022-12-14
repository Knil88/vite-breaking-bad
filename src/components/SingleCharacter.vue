<script >
   export default{
        name:"SingleCharacter",
        props:["info"],
       
   }
</script>

<template>
    <main>
      
            <section id="card-container">
                
                <div class="big-card">
                    <img :src="info.image" alt="">
                    <div>
                        <h4>{{info.name}}</h4>
                    </div>
                    <div id="">
                        {{info.species}}
                    </div>
                    <div>
                        {{info.status}}
                    </div>
                </div>
          
            </section>
      </main>

</template>

<style lang="scss" scoped>
div{
    margin: 5px auto;
}
#count{
    padding: 5px;
    background-color: aliceblue;
}

</style>
