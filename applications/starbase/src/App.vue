<template>
    <div id="app">
        <h3>{{title}}</h3>
        <Charactor />
    </div>
</template>

<script>
import Charactor from "./components/Character";

export default {
  name: "app",
  data() {
    return {
      title: "Generate Your Team"
    };
  },
  methods: {
      
  },
  components: {
      Charactor
  }
};
</script>
