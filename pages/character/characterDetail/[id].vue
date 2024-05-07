<script setup lang="ts">
import type { Character } from "@/interfaces";

const route = useRoute();

const characterList = useState<Map<number, Character>>("characterList");

const character = computed(() => {
  return characterList.value.get(Number(route.params.id)) as Character;
});
</script>

<template>
  <nav id="breadcrumbs">
    <ul>
      <li>
        <NuxtLink :to="{ name: 'index' }">TOP</NuxtLink>
      </li>
      <li>
        <NuxtLink :to="{ name: 'character-characterList' }"
          >キャラクターリスト</NuxtLink
        >
      </li>
      <li>{{ character.name }}</li>
    </ul>
  </nav>
  <section>
    <h2>キャラクター詳細情報</h2>

    <table>
      <tr>
        <td>No:</td>
        <td>{{ character.id }}</td>
      </tr>
      <tr>
        <td>名前:</td>
        <td>{{ character.name }}</td>
      </tr>
      <tr>
        <td>懸賞金:</td>
        <td>{{ character.bounty }}ベリー</td>
      </tr>
    </table>
  </section>
</template>
