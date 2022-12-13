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
                <h1 class="is-size-1">{{ this.ingredient }}</h1>
                <p>{{ info[0]  }}</p>
            </div>
        </div>
    </div>
    <br>
    <div class="card-wrap">
<div class="card">
  <div class="card-image">
    <figure class="image is-4by3">
      <img src="https://bulma.io/images/placeholders/11x960.png" alt="Placeholder image">
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
        <p class="title is-4">John Smith</p>
        <p class="subtitle is-6">@johnsmith</p>
      </div>
    </div>

    <div class="content">
      Lorem ipsum dolor sit amet, consectetur adipiscing elit.
      Phasellus nec iaculis mauris. <a>@bulmaio</a>.
      <a href="#">#css</a> <a href="#">#responsive</a>
      <br>
      <time datetime="2016-1-1">11:09 PM - 1 Jan 2016</time>
    </div>
  </div>
</div>

        
    </div>
</div>
</template>

<style scoped>
    .results-column {
        overflow: scroll;
    }
    .main-wrap {
        height: 500px;
        width: 80vw;
        background-color: pink;
    }
</style>