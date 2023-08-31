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

function toTitleCase(str) {
  return str.replace(/\w\S*/g, (txt) => {
    return txt.charAt(0).toUpperCase() + txt.substr(1).toLowerCase();
  });
}

definePageMeta({
  layout: "custom",
});
</script>
