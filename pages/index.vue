<script setup lang="ts">
const { find } = useStrapi();

const { data, pending, error } = await useAsyncData("player", async () => {
  return await find("players", { populate: "data.id" });
});
</script>

<template>
  <div>
    <pre> {{ data }}</pre>
  </div>
</template>

<style></style>
