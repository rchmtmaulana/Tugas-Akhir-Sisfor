<script setup>
import { ref, computed, onMounted } from 'vue';

const endpoint = "http://localhost:8055/items/Galeri"
const galeriData = ref([]);

const itemsPerPage = ref(3);
const currentPage = ref(0);
const totalPages = computed(() => Math.ceil(galeriData.value.length / itemsPerPage.value));

async function getGaleri() {
  const api = await fetch(endpoint)
  const data = await api.json()
  console.log(data.data)
  galeriData.value = data.data;
}

onMounted(() => {
  getGaleri();
})

const getImageUrl = (imageName) => {
  return `http://localhost:8055/assets/${imageName}`;
};

const visibleItems = computed(() => {
  const start = currentPage.value * itemsPerPage.value;
  const end = start + itemsPerPage.value;
  return galeriData.value.slice(start, end);
});

const prevPage = () => {
  if (currentPage.value > 0) {
    currentPage.value--;
  }
};

const nextPage = () => {
  if (currentPage.value < totalPages.value - 1) {
    currentPage.value++;
  }
};
</script>

<template >
    <section class="galeri flex justify-center relative" style="height: 470px">
      <div class="content offside max-w-screen-xl w-full bg-white border rounded-xl overflow-hidden" style="height: 520px">
        <div class="pb-5">
          <h1 class="font-bold pt-5 text-center" style="font-family: Times New Roman Thin; font-size: 40px">Galeri</h1>
        </div>
        <div class="w-full mt-6">
          <div class="px-6 overflow-hidden">
            <div class="grid grid-cols-3 gap-4">
              <div v-for="(item, index) in visibleItems" :key="item.id" class="mb-4">
                <img :src="getImageUrl(item.gambar)" alt="Image" class="w-full h-60 object-cover" />
                <div class="mt-2" v-html="item.konten" style="font-family: Roboto; font-weight: bold;"></div>
              </div>
            </div>
            <div class="flex justify-between mt-4">
              <button @click="prevPage" :disabled="currentPage === 0" class="text-gray-500 cursor-pointer" style="font-family: Roboto; font-weight: bold;">&lt; Sebelumnya</button>
              <button @click="nextPage" :disabled="currentPage === totalPages - 1" class="text-gray-500 cursor-pointer" style="font-family: Roboto; font-weight: bold;">Selanjutnya &gt;</button>
            </div>
          </div>
        </div>
      </div>
    </section>
</template>