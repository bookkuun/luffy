<script setup lang="ts">
import type { Character } from "@/interfaces";

const characterList = useState<Map<number, Character>>("characterList");

// 懸賞金の合計を計算する
const totalBounty = computed((): number => {
  let total = 0;
  for (const character of characterList.value.values()) {
    total += character.bounty;
  }
  return total;
});
</script>

<template>
  <section>
    <h1>キャラクター名</h1>
    <p>懸賞金合計：{{ totalBounty }}ベリー</p>
    <OneCharacter2 v-for="id in characterList.keys()" :key="id" :id="id" />
  </section>
</template>

<style>
section {
  border: blue 5px solid;
  margin: 10px;
}
</style>
