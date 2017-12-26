<template >
    <div id="app">
        <h3>{{title}}</h3>
        <div class="row">

        <Charactor 
            v-for="(id, index) in initial_id"
            v-bind:id="id"
            v-bind:key="index"
        />

        </div>
    </div>
</template>

<script>
import Charactor from "./components/Character";

export default {
  name: "app",
  data() {
    return {
      title: "Generate Your Team",
      initial_id: [1, 13, 14]
    };
  },
  components: {
    Charactor
  }
};
</script>
