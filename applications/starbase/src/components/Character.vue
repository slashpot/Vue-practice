<template>
  <div class="col-sm" @click="generateRandomCharacter">
      <div class="character-card">
          <div class="card-block">
              <h4 class="card-title">{{Character.name}}</h4>
              <p class="card-text">Height: {{Character.height}}cm</p>
              <p class="card-text">Mass: {{Character.mass}}kg</p>
              <p class="card-text">Hair Color: {{Character.hair_color}}</p>
              <p class="card-text">Eye Color: {{Character.eye_color}}</p>
          </div>
      </div>
  </div>
</template>

<script>
export default {
  props: ["id"],
  data() {
    return {
      Character: {}
    };
  },
  methods: {
    fetchCharacter(id) {
      fetch(`https://swapi.co/api/people/${id}`, {
        method: "GET"
      })
        .then(response => response.json())
        .then(data => (this.Character = data));
    },
    generateRandomCharacter() {
        let randomId = Math.floor(Math.random() * 83) + 1;
        this.fetchCharacter(randomId);
    }
  },
  created() {
    this.fetchCharacter(this.id);
  }
};
</script>
