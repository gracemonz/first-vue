<template>
  <div>
    <button v-on:click="limit"
      class="bg-transparent hover:bg-blue-500 text-blue-700 font-semibold hover:text-white py-2 px-4 border border-blue-500 hover:border-transparent rounded"
    >Limit to 2</button>
    <div v-for="film in films" :key="film.id">
      
      <div class="max-w-full rounded overflow-hidden shadow-lg">
        <div class="px-6 py-4">
          <div class="font-bold text-xl mb-2">{{film.title}}</div>
          <span class="text-gray-700 text-base">Description:</span>
          <span class="text-gray-700 text-base">{{film.description}}</span>
          {{film.director}}
          {{film.producer}}
          {{film.release_date}}
          {{film.rt_score}}
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Axios from "axios";
export default {
  name: "MainContent",
  mounted() {
    Axios.get(this.BaseUrl + "/films").then(response => {
      this.films = response.data;
    });
    limitc;
  },
  data() {
    return {
      BaseUrl: "https://ghibliapi.herokuapp.com",
      films: {},
      FilmString: "/films/"
    };
  },
  methods: {
    limit() {
      Axios.get(this.BaseUrl + this.FilmString + "?limit=2").then(reponse => {
        this.films = reponse.data;
      });
    }
  }
};
</script>