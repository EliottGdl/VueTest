<template>
  <div class="home">
    <h1> All Destinations </h1>
    <div class="destinations">
    <div v-for="destination in destinations" :key="destination.name">
      <router-link :to="{name : 'DestinationDetails',params:{slug:destination.slug}}">
        <h2>{{destination.name}}</h2>
      </router-link>
      <figure>
        <router-link :to="{name : 'DestinationDetails',params:{slug:destination.slug}}">
          <img class="shake-slow" :src="require(`@/assets/${destination.image}`)" :alt="destination.name">
        </router-link>
      </figure>
    </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import store from "@/store.js";
export default {
  name: "Home",
  components: {},
  data() {
    return { destinations: store.destinations };
  }
};
</script>

<style scoped>

@import '../assets/styles/csshake-slow.min.css';

.home{
  max-width:1600px;
  margin : 0 auto;
}

img {
  max-width:300px;
}

.destinations {
  display:flex;
  align-items: center;
  justify-content:center;
  flex-wrap: wrap;
}

a {
  color : cornflowerblue;
  text-decoration: none;
  font-size:20px;
}

a:hover {
  text-decoration: underline;
}

a:visited {
  text-decoration: underline;
}

</style>