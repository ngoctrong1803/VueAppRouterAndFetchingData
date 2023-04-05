<template>
  <nav>
    <router-link to="/">Home</router-link> |
    <router-link :to="{ name: 'about' }">About |</router-link>
    <router-link :to="{ name: 'jobs' }">Jobs</router-link>

    <div style="padding-top: 15px;">
      <button @click="redirect">Redirect</button>
      <button @click="back">Go Back</button>
      <button @click="forward">Go forward</button>
    </div>
  </nav>
  <router-view/>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
// eslint-disable-next-line import/no-unresolved

export default defineComponent({
  name: 'App',
  methods: {
    // eslint-disable-next-line @typescript-eslint/no-empty-function
    redirect() {
      this.$router.push({ name: 'home' });
    },
    // eslint-disable-next-line @typescript-eslint/no-empty-function
    back() {
      this.$router.go(-1);
    },
    // eslint-disable-next-line @typescript-eslint/no-empty-function
    forward() {
      this.$router.go(1);
    },
  },
});
</script>
<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #42b983;
}
</style>
