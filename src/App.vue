<template>
  <div id="app">
    <div class="container mt-5">
      <div class="title">
        <h2>{{ title }}</h2>
        <h6>{{subtitle}}</h6>
      </div>

      <div class="team row">
        <Character v-for="(id, index) in initial_ids" :id="id" v-bind:key="index"></Character>
      </div>
    </div>
    <div class="footer-bottom clearfix">
      <div class="container copyright">
        <p class="pb-0 mb-0">
          Copyright © 2022 | developed by
          <a href="index.html">nancy khaled</a>, All Right
          Reserved.
        </p>
      </div>
    </div>
  </div>
</template>

<script>
import Character from "./components/Character.vue";

export default {
  name: "app",
  data() {
    return {
      title: "generate your team",
      subtitle: "(star war)",
      initial_ids: [1, 5, 10, 15, 20, 25]
    };
  },
  components: {
    Character
  }
};
</script>

