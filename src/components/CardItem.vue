<script setup>
defineProps({
  card: Object,
})
</script>

<template>
  <div class="card-item">
    <h2>{{ card.name }}</h2>
    <p>Type: {{ card.type }}</p>
    <p>Rarity: {{ card.rarity }}</p>
    <p>Set: {{ card.set }}</p>
  </div>
</template>

<style scoped>
.card-item {
  border: 1px solid var(--color-border);
  border-radius: 8px;
  padding: 1rem;
}
</style>
