<template>
  <div class="job">
   <h1>Job detail</h1>
   <h2>The job id is {{ id }}</h2>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
// eslint-disable-next-line import/no-unresolved

export default defineComponent({
  name: 'JobDetailView',
  // props: ['id'],
  components: {
  },
  data() {
    return {
      id: this.$route.params.id,
    };
  },
});
</script>

<style>
.job h2 {
    background: #f4f4f4;
    padding: 20px;
    border-radius: 10px;
    margin: 10px auto;
    max-width: 600px;
    cursor: pointer;
    color: #444;
}
.job h2:hover {
    background: #ddd;
}
.job a {
    text-decoration: none;
}

button {
  margin: 0 10px;
  padding: 10px;
  border: none;
  border-radius: 4px;
}
</style>
