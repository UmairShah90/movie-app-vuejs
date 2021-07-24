<template>
  <div class="movie-detial">
    <h2>{{ movie.Title }}</h2>
    <p>{{ movie.Year }}</p>
    <img :src="movie.Poster" alt="movie poster" class="featured-img" />
    <p>{{ movie.Plot }}</p>
  </div>
</template>

<script>
import { ref, onBeforeMount } from "vue";
import { useRoute } from "vue-router";
import env from "@/env.js";

export default {
  setup() {
    const movie = ref({});
    const route = useRoute();

    onBeforeMount(() => {
      fetch(
        `http://www.omdbapi.com/?apikey=${env.apikey}&i=${route.params.id}&plot=full`
      )
        .then((response) => response.json())
        .then((data) => {
          movie.value = data;
        });
    });

    return { movie };
  },
};
</script>

<style lang="scss">
.movie-detial {
  padding: 20px;

  h2 {
    display: flex;
    justify-content: center;
    font-size: 28px;
    font-weight: 600;
    margin-bottom: 16px;
    align-items: center;
    color: red;
  }
  .featured-img {
    display: flex;
    border-radius: 5px;
    align-items: center;
    justify-content: center;
    max-width: 300px;
    margin: 0 auto;
    margin-bottom: 16px;
  }
  p {
    display: flex;
    align-items: center;
    justify-content: center;
    color: #333;
    font-size: 18px;
    line-height: 1.4;

    &p::first-letter{
     color:red;
    }
    
  }
  
}
</style>
