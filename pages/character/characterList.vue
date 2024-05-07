<script setup lang="ts">
import type { Character } from "@/interfaces";

const characterList = useState<Map<number, Character>>("characterList");
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
    </ul>
  </nav>
  <section>
    <h2>キャラクターリスト</h2>
    <NuxtLink :to="{ name: 'character-characterAdd' }">こちら </NuxtLink>から
    <section>
      <ul>
        <li v-for="[id, character] in characterList" :key="id">
          <NuxtLink
            :to="{ name: 'character-characterDetail-id', params: { id: id } }"
          >
            {{ character.name }}
            No:{{ id }} {{ character.name }}
          </NuxtLink>
        </li>
      </ul>
    </section>
  </section>
</template>
