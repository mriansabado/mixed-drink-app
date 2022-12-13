<script>
import axios from 'axios';
export default {
    data() {
        return {
            results: [],
            ingredient: ""
        }
    },
    methods: {
        getData() {
            axios.get("https://www.thecocktaildb.com/api/json/v1/1/search.php?s=" + this.ingredient)
            .then(response => {
                this.results = response.data;
            })
            .catch(error => {
                console.log('There is an error')
            })
        }
    }
}
</script>

<template>
<div>
    <div class="box main-wrap">
        <div class="box">
            <input type="text" v-model="ingredient" placeholder="enter ingredient...">
            <button @click="getData" class="button is-info">Get Info</button>
        </div>
        <div class="box results-column">
            <div v-for="info in results">
                    <div class="card-wrap">
                        <div class="card">
                        <div class="card-image">
                            <figure class="image is-4by3 main-image">
                            <img v-bind:src="info[0].strDrinkThumb" alt="Placeholder image">
                            </figure>
                        </div>
                        <div class="card-content">
                            <div class="media">
                            <div class="media-left">
                                <figure class="image is-12x12">
                                <img src="https://bulma.io/images/placeholders/96x96.png" alt="Placeholder image">
                                </figure>
                            </div>
                            <div class="media-content">
                                <p class="title is-4">{{ info[0].strDrink }}</p>
                                 <div class="content">
                                    {{ info[0].strInstructions }}
                                    <br>
                                    {{ info[0].strIngredient1 }},
                                    {{ info[0].strIngredient2 }},
                                    {{ info[0].strIngredient3 }},
                                    {{ info[0].strIngredient4 }},
                                    {{ info[0].strIngredient5 }}
                                 </div>
                            </div>
                            </div>

                           
                        </div>
                        </div>
                    </div>
            </div>
        </div>
    </div>
    <br>

</div>
</template>

<style scoped>
    .results-column {
        overflow: scroll;
    }
    .main-wrap {
        height: 600px;
        width: 80vw;
        background-color: pink;
    }
    .main-image {
        display: flex;
    }
   
</style>