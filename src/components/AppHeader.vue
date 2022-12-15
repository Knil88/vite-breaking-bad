<script >
    export default{
        props: ["msg"],
        data() {
            return {
                image:"https://vectorlogo4u.com/wp-content/uploads/2020/11/Rick-and-Morty-Logo-Vector-01.png",
            }
        },
    }
</script>

<template>
 <header>
    
       
       <img :src="image" alt="" id="logo"> 
   
   
    <h1>
        {{msg}}
    </h1>
 </header>
</template>

<style lang="scss" scoped>
header{
    display: flex;
}   
#logo{
        max-width: 200px;
    }
</style>
