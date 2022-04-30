<template>
  <div class="col-md-4">
    <div class="character-card card mb-3">
      <div class="card-body">
        <h4 class="card-title">{{character.name}}</h4>
        <p class="card-text"><span class="text-muted">gender: </span>{{character.gender}}</p>
        <p class="card-text"><span class="text-muted">height: </span>{{character.height}} cm</p>
        <p class="card-text"><span class="text-muted">mass: </span>{{character.mass}} kg</p>
        <p class="card-text"><span class="text-muted">hair color: </span>{{character.hair_color}}</p>
        <p class="card-text"><span class="text-muted">eye color: </span>{{character.eye_color}}</p>
        <button class="btn btn-success"  @click="switchCharacter">switch character</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["id"],
  data() {
    return {
      character: {}
    };
  },
  methods: {
    fetchCharacter(id) {
      fetch(`https://swapi.dev/api/people/${id}`, {
        method: "GET"
      })
        .then(response => response.json())
        .then(json => (this.character = json));
    },
    switchCharacter() {
      let random_id = Math.floor(Math.random() * 82) + 1;
      this.fetchCharacter(random_id);
    }
  },
  created() {
    this.fetchCharacter(this.id);
  }
};
</script>
