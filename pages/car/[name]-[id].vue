<template>
  <div>
    <CarDetailHero />

    <CarDetailAtributes />

    <CarDetailDescription />

    <CarDetailContact />
  </div>
</template>

<script setup>
const route = useRoute();
const { toTitleCase } = useUtilites();
useHead({
  title: toTitleCase(route.params.name),
});

definePageMeta({
  layout: "custom",
});
</script>
