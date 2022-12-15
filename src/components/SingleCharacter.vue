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
                    <div id="info-container">
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
                </div>
          
            </section>
      </main>

</template>

<style lang="scss" scoped>
div{
    margin: 5px ;
}
#count{
    padding: 5px;
    background-color: aliceblue;
}
#info-container{
    
        padding-left: 45px;
}

</style>
