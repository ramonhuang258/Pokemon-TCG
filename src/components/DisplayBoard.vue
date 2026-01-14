<template>
  <div class="display-board-container">
    <div v-for="item in items" :key="item.id">
      <slot :item="item" />
    </div>
  </div>
</template>

<script>
export default {
  name: 'DisplayBoard',
  props: {
    items: {
      type: Array,
      required: true,
    },
  },
}
</script>

<style scoped>
.display-board-container {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 1rem;
  background-color: rgb(231, 231, 231);
  padding: 0.5rem;
  border: 0.5rem solid black;
  margin-top: 1.5rem;
}
</style>
