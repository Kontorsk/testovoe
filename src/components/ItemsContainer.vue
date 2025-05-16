<template>
  <ul class="items-wrapper">
    <li
      v-for="item in data"
      :key="item.id"
      class="item"
      @click="selectItem(item)"
    >
      <h3>{{ item.name }}</h3>
    </li>
  </ul>
</template>

<script setup>
defineProps({
  data: {
    type: Array,
    required: true,
  },
});

const emit = defineEmits(['selectItem']);

const selectItem = (item) => {
  emit('selectItem', item);
};
</script>

<style scoped>
.items-wrapper {
  padding: 16px;
  list-style: none;
  border: 3px solid;
  width: 520px;
}

.item {
  display: inline-block;
  border: 2px dashed;
  margin: 10px;
  width: 80px;
  text-align: center;
}
</style>
