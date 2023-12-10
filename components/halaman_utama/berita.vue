<script setup>
import { ref, computed, onMounted } from 'vue';

const endpoint = "http://localhost:8055/items/Berita?sort=id&filter={%22id%22:{%22_gte%22:1,%22_lte%22:4}}"
const beritaData = ref([]);

async function getBerita() {
  const api = await fetch(endpoint)
  const data = await api.json()
  console.log(data.data)
  beritaData.value = data.data;
}

onMounted(() => {
  getBerita();
})

const getImageUrl = (imageName) => {
  return `http://localhost:8055/assets/${imageName}`;
};
</script>

<template>
    <section class="berita flex justify-center relative" style="height: 1150px">
      <div class="content offside mt-4 max-w-screen-xl w-full bg-white overflow-hidden rounded-xl" style="height: 1050px">
        <h1 class="text-2xl font-bold py-8 text-center mb-10" style="font-size: 40px; font-family: Times New Roman Thin">Berita</h1>
        <div id="berita" class="grid grid-cols-2" style="margin-left: 100px;">
          <div v-for="item in beritaData" :key="item.id">
            <img :src="getImageUrl(item.gambar)" :alt="`berita ${item.id}`" class="w-full object-cover rounded-md" style="width: 500px; height: 280px;" />
            <div style="margin-bottom: 50px;">
              <h1 class="font-bold mt-2" style="font-size: 17px; padding-right: 100px;" v-html="item.judul"></h1>
              <div class="flex items-center">
                <img src="/calendar.jpg" alt="error" class="w-4 h-4 mr-2" />
                <p class="text-sm text-grey">{{ item.tanggal }}</p>
              </div>
            </div>
          </div>
        </div>
        <div class="mt-2 flex justify-center">
          <button class="rounded-xl px-6 py-3 bg-gray-800 text-white">
            <NuxtLink to="/profil/berita">SELENGKAPNYA</NuxtLink>
          </button>
        </div>
      </div>
    </section>
</template>