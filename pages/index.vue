<script setup lang="ts">
import type { ActiveStock } from "~/utils/type";

const fetchData = async (): Promise<ActiveStock[]> => {
  const data = await $fetch<ActiveStock[]>(
    "https://financialmodelingprep.com/api/v3/stock_market/actives?apikey=Ai7NmAPUE7MqHIsSWf4dgsoSvOa658He"
  );

  console.log(data);
  return data.slice(0, 10);
};

const activeStocks = ref<ActiveStock[]>([]);
onMounted(async () => {
  activeStocks.value = await fetchData();
});
</script>

<template>
  <div class="">
    <div>index page</div>
  </div>
</template>
