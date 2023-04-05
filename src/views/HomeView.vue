<template>
  <div class="home">
    <HomeHeader/>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
// eslint-disable-next-line import/no-unresolved
import HomeHeader from '@/components/HomeHeader.vue'; // @ is an alias to /src

export default defineComponent({
  name: 'HomeView',
  components: {
    HomeHeader,
  },
});
</script>
