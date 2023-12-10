<script setup>
import { ref, computed, onMounted } from 'vue';

const endpoint = "http://localhost:8055/items/Informasi"
const informasiData = ref([]);

async function getInformasi() {
  const api = await fetch(endpoint)
  const data = await api.json()
  console.log(data.data)
  informasiData.value = data.data;
}

onMounted(() => {
  getInformasi();
})

const getImageUrl = (imageName) => {
  return `http://localhost:8055/assets/${imageName}`;
};
</script>

<template>
  <section class="informasi items-center -mt-32 justify-center bg-blue-700 py-16" style="background-color: rgb(26, 46, 107);">
    <div class="container mx-auto">
      <h1 class="text-2xl mb-24 text-center text-white" style="font-size: 40px; font-family: Times New Roman Thin">
        Informasi
      </h1>

      <!-- Two-column layout with three rows using Tailwind CSS classes -->
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-2 xl:grid-cols-2 gap-8">
        <div v-for="(item, index) in informasiData" :key="index" class="mb-8">
          <img :src="getImageUrl(item.gambar)" alt="" class="rounded-xl mb-4 mx-auto" style="height: 250px" />
          <h4 class="text-center text-white font-bold text-lg" style="font-size: 19px; padding-right: 150px; padding-left: 150px;">
            {{ item.judul }}
          </h4>
        </div>
      </div>

      <div class="mt-12 flex justify-center">
        <button class="rounded-xl px-6 py-3 bg-gray-800 text-white">
          SELENGKAPNYA
        </button>
      </div>
    </div>
  </section>
</template>