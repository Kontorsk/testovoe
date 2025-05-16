<template>
  <div>
    <ItemsContainer
      :data="selectedItems"
      class="selected-list"
    />
    <ItemsContainer
      :data="data"
      @selectItem="(item) => selectUserItem(item)"
    />
  </div>
</template>

<script setup>
import { ref } from 'vue';
import ItemsContainer from './ItemsContainer.vue';

const props = defineProps({
  data: {
    type: Array,
    required: true,
  },
});

const selectedItems = ref([]);

const selectUserItem = (item) => {
  const isIncorrectItem =
    selectedItems.value.length >= 6 || selectedItems.value.includes(item.id);

  if (isIncorrectItem) return;

  const selectedItem = props.data.find((userItem) => userItem === item);
  selectedItems.value.push(selectedItem);
};
</script>

<style scoped>
.selected-list {
  width: 315px;
  height: 265px;
  margin-top: 0;
  margin-bottom: 48px;
  padding: 0;
}
</style>
