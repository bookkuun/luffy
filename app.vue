<script setup lang="ts">
interface Character {
  id: number;
  name: string;
  bounty: number;
}

const characterListInit = new Map<number, Character>();
characterListInit.set(1, { id: 1, name: "ルフィ", bounty: 150000000 });
characterListInit.set(2, { id: 2, name: "ゾロ", bounty: 320000000 });
characterListInit.set(3, { id: 3, name: "ナミ", bounty: 66000000 });

const characterList = ref(characterListInit);

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
    <OneCharacter
      v-for="[id, character] in characterList"
      :key="id"
      :name="character.name"
      :bounty="character.bounty"
    />
  </section>
</template>

<style scoped>
section {
  border: blue 5px solid;
  margin: 10px;
}
</style>
