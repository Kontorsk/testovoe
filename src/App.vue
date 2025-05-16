<template>
  <div class="items-workspace">
    <UserWorkspace :data="userItems" />
    <ItemsCatalog :data="allItems" />
  </div>
</template>

<script setup>
import { ref } from 'vue';
import UserWorkspace from './components/UserWorkspace.vue';
import ItemsCatalog from './components/ItemsCatalog.vue';

const userItems = ref(createData('Shoes'));
const allItems = ref(createData('Jacket'));

function createData(title) {
  return Array.from({ length: 10 }, (_, i) => ({
    id: i,
    name: `${title} ${++i}`,
  }));
}
</script>

<style scoped>
.items-workspace {
  display: flex;
  margin: 48px 320px;
  justify-content: space-between;
  width: auto;
}
</style>
