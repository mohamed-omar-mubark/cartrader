<script setup>
const route = useRoute();
const minPrice = computed(() => route.query.minPrice);
const maxPrice = computed(() => route.query.maxPrice);
const { data: cars, refresh } = await useFetchCars(route.params.city, {
  minPrice,
  maxPrice,
  make: route.params.make,
});

watch(
  () => route.query,
  () => refresh()
);
</script>

<template>
  <div>
    <CarCards v-if="cars?.length" :cars="cars" />
    <h1 v-else class="text-red-600">No cars found for this filters</h1>
  </div>
</template>
