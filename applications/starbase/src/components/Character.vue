<template>
  <div>
      {{Character}}
  </div>
</template>

<script>
export default {
  data() {
    return {
      Character: {}
    };
  },
  methods: {
    fetchCharacter() {
      fetch("https://swapi.co/api/people/1", {
        method: "GET"
      })
        .then(response => response.json())
        .then(data => (this.Character = data));
    }
  },
  created() {
      this.fetchCharacter();
  }
};
</script>
