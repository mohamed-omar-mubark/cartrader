<template>
  <div>
    <!-- car detail hero -->
    <CarDetailHero />

    <!-- car attributes -->
    <CarDetailAttributes />

    <!-- car description -->
    <CarDetailDescription />

    <!-- car contact -->
    <CarDetailContact />
  </div>
</template>

<script setup>
const route = useRoute();
const { toTitleCase } = useUtilities();

useHead({
  title: toTitleCase(route.params.name),
});

definePageMeta({
  layout: "custom",
});
</script>
