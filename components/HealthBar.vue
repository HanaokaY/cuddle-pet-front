<template>
  <div class="health-bar">
    <div class="health-bar-inner" :style="{ width: healthPercentage }"></div>
  </div>
</template>

<script lang="ts">
import { Vue, Component, Prop } from 'nuxt-property-decorator';

@Component
export default class HealthBar extends Vue {
  @Prop({ default: 100 }) health!: number;

  get healthPercentage() {
    return `${this.health}%`;
  }
}
</script>

<style scoped>
.health-bar {
  width: 200px;
  height: 20px;
  background-color: #ddd;
  border-radius: 5px;
  overflow: hidden;
}

.health-bar-inner {
  height: 100%;
  background-color: #ff0000;
  transition: width 0.3s;
}
</style>
