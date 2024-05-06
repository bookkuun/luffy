<script setup lang="ts">
interface Props {
  id: number;
  name: string;
  bounty: number;
}

type Emits = {
  incrementBounty: [id: number];
};

const props = defineProps<Props>();
const emit = defineEmits<Emits>();

const bountyUp = () => {
  emit("incrementBounty", props.id);
};
</script>

<template>
  <section class="box">
    <p>{{ name }}</p>
    <p>懸賞金：{{ bounty }}ベリー</p>
    <button @click="bountyUp">懸賞金アップ</button>
  </section>
</template>

<style scoped>
.box {
  border: black 5px solid;
  margin: 3px;
  padding: 10px;
}
</style>
