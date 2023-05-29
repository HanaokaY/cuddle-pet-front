<template>
  <div class="tamagotchi">
    <img src="~/assets/egg.png" alt="Tamagotchi" class="img" />
  </div>
</template>

<script lang="ts">
import { Vue, Component } from 'nuxt-property-decorator';

@Component
export default class Tamagotchi extends Vue {}
</script>

<style scoped>
.tamagotchi {
  text-align: center;
}

.img {
  width: 100%;
  animation: shake 1s ease-in-out infinite alternate;
}

@keyframes shake {
  0% {
    transform: translateX(-3px) rotate(-1deg);
  }
  50% {
    transform: translateX(3px) rotate(1deg);
  }
  100% {
    transform: translateX(-3px) rotate(-1deg);
  }
}

</style>
