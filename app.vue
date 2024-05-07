<script setup lang="ts">
import type { Character } from "@/interfaces";

useState<Map<number, Character>>(
  "characterList",
  (): Map<number, Character> => {
    const characterListInit = new Map<number, Character>();
    characterListInit.set(1, { id: 1, name: "ルフィ", bounty: 150000000 });
    characterListInit.set(2, { id: 2, name: "ゾロ", bounty: 320000000 });
    characterListInit.set(3, { id: 3, name: "ナミ", bounty: 66000000 });
    return characterListInit;
  }
);
</script>

<template>
  <!-- <BaseSection /> -->
  <header><h1>ワンピース</h1></header>
  <main><NuxtPage /></main>
</template>

<style>
main {
  border: black 5px solid;
  padding: 10px;
}

#breadcrumbs ul li {
  display: inline;
  list-style-type: none;
}

#breadcrumbs ul {
  padding-left: 0px;
}

#breadcrumbs ul li::before {
  content: " > ";
}

#breadcrumbs ul li:first-child::before {
  content: none;
}
</style>
