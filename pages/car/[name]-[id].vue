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

useHead({
  title: toTitleCase(route.params.name),
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
