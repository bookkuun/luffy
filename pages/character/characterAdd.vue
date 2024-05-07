<script setup lang="ts">
import type { Character } from "@/interfaces";

const rooter = useRouter();

const characterList = useState<Map<number, Character>>("characterList");

const character: Character = reactive({
  id: 0,
  name: "",
  bounty: 0,
});

const addCharacter = () => {
  characterList.value.set(character.id, character);
  rooter.push({ name: "character-characterList" });
};
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
      <li>キャラクター追加</li>
    </ul>
  </nav>
  <section>
    <h2>キャラクター追加</h2>
    <p>新しいキャラクターを追加します。</p>
    <form @submit.prevent="addCharacter">
      <!-- id項目も -->
      <label for="id">No:</label>
      <input type="number" id="id" v-model="character.id" />
      <p></p>
      <label for="name">名前:</label>
      <input type="text" id="name" v-model="character.name" />
      <p></p>
      <label for="bounty">懸賞金:</label>
      <input type="number" id="bounty" v-model="character.bounty" />
      <button type="submit">追加</button>
    </form>
  </section>
</template>
