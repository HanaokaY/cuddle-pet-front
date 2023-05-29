<template>
  <div>
    <PlayField/>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import PlayField from '~/components/PlayField.vue';
export default Vue.extend({
  name: 'IndexPage',
  components: {
    PlayField
  }
})
</script>

<style scoped>
  div {
    background-image: url('~/assets/heart_bg.png');
    background-size: cover;
    background-position: center;
  }
</style>
