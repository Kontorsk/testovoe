<template>
  <div class="card-wrapper">
    <h1
      v-if="item"
      class="card-title"
    >
      {{ item.name }}
    </h1>
  </div>
</template>

<script setup>
defineProps({
  item: {
    type: Object,
    default: null,
  },
});
</script>

<style scoped>
.card-wrapper {
  border: 3px solid;
  width: 315px;
  height: 265px;
  margin-bottom: 48px;
  margin-left: auto;
}

.card-title {
  text-align: center;
  font-size: 64px;
  margin-top: 90px;
}
</style>
