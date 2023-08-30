<template>
  <div>
    <NavBar />

    <div
      class="mx-auto mt-4 max-w-7xl space-y-4 px-4 xs:px-8 sm:px-10 lg:px-16 pb-16 w-3/5"
    >
      <div class="mt-32 flex">
        <!-- car side bar -->
        <CarSideBar />

        <NuxtPage />
      </div>
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
</script>
