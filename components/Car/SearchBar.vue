<template>
  <div
    class="font-serif w-[1000px] text-2xl rounded-full bg-white flex justify-between overflow-hidden drop-shadow-2xl mx-auto"
  >
    <input
      type="text"
      class="py-3 px-5 w-full text-2xl rounded-full focus:outline-none"
      :class="cityError ? 'border-red-500 border' : ''"
      placeholder="Search by city...."
      v-model="city"
      required
    />
    <button class="bg-indigo-500 px-10 text-white" @click="handleSubmit">
      Search
    </button>
  </div>
</template>

<script setup>
const city = ref("");
const cityError = ref(false);

const handleSubmit = () => {
  if (!city.value) {
    return (cityError.value = true);
  }
  navigateTo(`/city/${city.value}/car`);
};
</script>
