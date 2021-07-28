<template>
    <div>
        <h1>Test Menu</h1>
        <button v-on:click="generateMenu">Test Button</button>
      
    </div>
</template>

<script>
const axios = require('axios').default;
export default {
    name: "Menu",
    methods:{
        generateMenu(){
            console.log('ran')
                  
                 
            var options = {
                method: 'GET',
                url: 'https://www.thecocktaildb.com/api/json/v1/1/search.php?f=a',
          
            };

            axios.request(options).then(function (response) {
                console.log(response.data);
            }).catch(function (error) {
                console.error(error);
            });


        },
                
    }, 
    data(){
        return {
            counter: 0, 

            

        }
    }
}
</script>

<style>

</style>