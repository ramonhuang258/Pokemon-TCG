<script setup>
defineProps({
  item: Object,
  required: true,
})
</script>

<template>
  <div class="expansion-item">
    <div class="expansion-logo"><img :src="item.imgSrc" :alt="item.name" /></div>
    <h2>{{ item.name }}</h2>
    <p>Code: {{ item.code }}</p>
    <p>Release Date: {{ item.releaseDate }}</p>
    <p>Number of Cards: {{ item.totalCards }}</p>
  </div>
</template>

<style scoped>
.expansion-item {
  border: 2px solid #ccc;
  border-radius: 8px;
  overflow: hidden;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  background-color: #fff;
  padding: 1rem;
  height: 100%;
}

.expansion-item:hover {
  background-color: aquamarine;
  cursor: pointer;
}

.expansion-logo img {
  width: 100%;
  aspect-ratio: 16 / 9;
  object-fit: contain;
}
</style>
