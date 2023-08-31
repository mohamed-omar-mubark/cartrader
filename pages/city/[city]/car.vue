<template>
  <div>
    <div class="mt-32 flex">
      <!-- car side bar -->
      <CarSideBar />

      <NuxtPage />
    </div>
  </div>
</template>

<script setup>
const route = useRoute();
const { toTitleCase } = useUtilities();

useHead({
  title: `${
    route.params.make ? toTitleCase(route.params.make) : "Cars"
  } in ${toTitleCase(route.params.city)}`,

  meta: [
    {
      name: "description",
      content: "Cartrader is a car rental company",
    },
  ],
});

definePageMeta({
  layout: "custom",
});
</script>
