<template>
  <div class="field">
    <div class="frame">
      <div class="sign">
        <p>{{ tamagotchiName }}</p>
      </div>
      <Tamagotchi />
    </div>
    <div class="actions">
      <button class="action-button feed-button" @click="feed">餌を与える</button>
      <button class="action-button play-button" @click="play">遊ぶ</button>
      <button class="action-button clean-button" @click="clean">掃除する</button>
    </div>
    <div>
        <HealthBar :health="pokemonHealth" />
    </div>
  </div>
</template>

<script lang="ts">
import { Vue, Component } from 'nuxt-property-decorator';
import Tamagotchi from '@/components/Tamagotchi.vue';
import HealthBar from '@/components/HealthBar.vue';

@Component({
  components: {
    Tamagotchi,
    HealthBar
  },
})
export default class Field extends Vue {
  tamagotchiName: string = 'みじんこっち';
  pokemonHealth: number = 100;

  mounted() {
    // 時間経過などにより体力を減少させる処理を実装する
    setInterval(() => {
      if (this.pokemonHealth > 0) {
        this.pokemonHealth -= 10;
      }
    }, 1000);
  }

  feed(): void {
    // 餌を与える処理
  }

  play(): void {
    // 遊ぶ処理
  }

  clean(): void {
    // 掃除する処理
  }
  
}
</script>

<style scoped>
.field {
  text-align: center;
}

.frame {
  display: inline-block;
  border: 50px solid #00bfff;
  background-color: transparent;
  padding: 50px;
  border-radius: 10px;
}

.sign {
  margin-bottom: 10px;
}

.actions {
  margin-top: 20px;
}

.action-button {
  background-color: #ff80ac;
  color: white;
  border: none;
  border-radius: 5px;
  padding: 10px 20px;
  font-size: 14px;
  cursor: pointer;
}

.feed-button {
  background-color: #ffd700;
}

.play-button {
  background-color: #00bfff;
}

.clean-button {
  background-color: #32cd32;
}
</style>
