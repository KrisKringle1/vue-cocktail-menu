<template>
    <div>
        <h1>Drink Menu</h1>
        <button v-on:click="generateMenu">generate drinks</button>
        <div class="container">
            <ul >
                <li v-for="drink in drinks" :key="drink.idDrink">Name: {{drink.strDrink}}</li>
            </ul>
        </div>
      
    </div>
</template>

<script>
const axios = require('axios').default;
export default {
    name: "Menu",
     data(){
        return {
            counter: 0,
            drinks: [],  

            

        }
    },
   
    methods:{
        generateMenu(){
            console.log(this.drinks)
            console.log(this.counter)
            
            var options = {
                method: 'GET',
                url: 'https://www.thecocktaildb.com/api/json/v1/1/search.php?f=a',
          
            };

            axios.request(options).then( (response) => {
                console.log('this counter', this.counter)
                console.log(response.data.drinks);
                this.drinks = response.data.drinks;
            }).catch(function (error) {
                console.error(error);
            });
        },
                
    }, 
   
}
</script>

<style>

</style>