<template>
  <h1>TOP</h1>
  <nav id="breadcrumbs">
    <ul>
      <li>TOP</li>
    </ul>
  </nav>
  <section>
    <p>
      <NuxtLink :to="{ name: 'character-characterList' }">
        キャラクターの設定はこちらから
      </NuxtLink>
    </p>
  </section>
</template>
