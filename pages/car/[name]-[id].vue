<template>
  <div v-if="car">
    <!-- car detail hero -->
    <CarDetailHero :car="car" />

    <!-- car attributes -->
    <CarDetailAttributes :features="car.features" />

    <!-- car description -->
    <CarDetailDescription :description="car.description" />

    <!-- car contact -->
    <CarDetailContact />
  </div>
</template>

<script setup>
const route = useRoute();
const { toTitleCase } = useUtilities();
const { cars } = useCars();

useHead({
  title: toTitleCase(route.params.name),
});

definePageMeta({
  layout: "custom",
});

const car = computed(() => {
  return cars.find((c) => {
    return c.id === parseInt(route.params.id);
  });
});
</script>
