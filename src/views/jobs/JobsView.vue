<template>
  <div class="jobs">
    <div v-for="job in jobs" :key="job.id" class="job">
      <router-link :to="{ name: 'jobsDetail', params: { id: job.id}  }">
        <h2>{{ job.title }}</h2>
      </router-link>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
// eslint-disable-next-line import/no-unresolved

export default defineComponent({
  name: 'JobView',
  components: {
  },
  data() {
    return {
      jobs: [],
    };
  },
  mounted() {
    fetch('http://localhost:3000/data')
      .then((res) => res.json())
      // eslint-disable-next-line no-return-assign
      .then((data) => this.jobs = data)
      .catch((error) => console.log(error.message));
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
</style>
