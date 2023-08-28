<script setup>
import { onMounted, ref } from "vue";

const status = ref("");

const getHealthcheck = async () => {
  const response = await fetch("http://localhost:8000/api/healthcheck");
  const data = await response.json();

  status.value = data;
};

onMounted(() => {
  getHealthcheck();
});
</script>

<template>
  <div>{{ status }}</div>
</template>

<style lang="scss" scoped></style>
