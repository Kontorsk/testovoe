<template>
  <div>
    <ItemCard :item="selectedItem" />
    <ItemsContainer
      :data="data"
      @selectItem="(item) => selectItem(item)"
    />
  </div>
</template>

<script setup>
import { ref } from 'vue';
import ItemCard from './ItemCard.vue';
import ItemsContainer from './ItemsContainer.vue';

defineProps({
  data: {
    type: Array,
    required: true,
  },
});

const selectedItem = ref();

const selectItem = (item) => {
  selectedItem.value = item;
};
</script>
