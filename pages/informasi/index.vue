<script setup>
import Header from "../components/halaman_utama/header.vue";
import Footer from "../components/halaman_utama/footer.vue";
import { ref, computed, onMounted } from 'vue';

const endpoint = "http://localhost:8055/items/Informasi"
const informasiData = ref([]);

const itemsPerPage = 6;
const currentPage = ref(1);

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

const paginatedInformasi = computed(() => {
  const start = (currentPage.value - 1) * itemsPerPage;
  const end = start + itemsPerPage;
  return informasiData.value.slice(start, end);
});

const totalPages = computed(() => Math.ceil(informasiData.value.length / itemsPerPage));

function changePage(page) {
  currentPage.value = page;
}
</script>

<template>
    <Header/>
    <div class="slug w-full text-white" style="height: 120px; margin-top: 130px; width: 100%; display: flex;">
        <NuxtLink to="/informasi">
            <img src="/home.png" alt="error" class="" style="margin: 0px 0px 0px 210px; padding-top: 28px; width: 30px; height: 60px;" />
            <p style="margin: 0px 0px 0px 5px; padding-top: 30px; font-size: 20px; font-family: Times New Roman Thin;">Informasi</p>
        </NuxtLink>
            <p style="margin: 0px 0px 0px 5px; padding-top: 30px; font-size: 20px; font-family: Times New Roman Thin;"> > Semua Informasi</p>
    </div>
    <div Style="background-color: #d3d3dd">
      <section class="flex justify-center relative" style="min-height: 850px">
        <div class="content offside max-w-screen-xl w-full bg-white border rounded-xl overflow-hidden" style="min-height: 900px; margin-top: -30px; position: relative;">
          <div class="pb-5">
            <h1 class="font-bold pt-5 text-center" style="font-family: Times New Roman Thin; font-size: 40px">Informasi</h1>
          </div>
          <div class="grid grid-cols-3 gap-16 mt-8 mx-10">
            <div v-for="informasi in paginatedInformasi" :key="informasi.id">
              <NuxtLink :to="'/informasi/' + informasi.id" class="flex flex-col items-center -my-4">
                <img :src="getImageUrl(informasi.gambar)" alt="News Image" style="height: 200px;" class="w-full h-40 object-cover mb-2" />
                <h2 class="text-lg font-semibold" v-html="informasi.judul" style="font-size: 15px;"></h2>
              </NuxtLink>
            </div>
          </div>
          <div class="absolute bottom-0 left-1/2 transform -translate-x-1/2 mb-20">
            <button @click="changePage(currentPage - 1)" :disabled="currentPage === 1" class="mx-2 px-6 py-2 rounded cursor-pointer" :class="{ 'bg-blue-500 text-white': currentPage > 1, 'bg-gray-200': currentPage === 1 }">&#8592; Sebelumnya</button>
            <button @click="changePage(currentPage + 1)" :disabled="currentPage === totalPages" class="mx-2 px-6 py-2 rounded cursor-pointer" :class="{ 'bg-blue-500 text-white': currentPage < totalPages, 'bg-gray-200': currentPage === totalPages }">Selanjutnya &#8594;</button>
          </div>
        </div>
      </section>
    </div>
    <Footer/>
</template>

<style>
.slug {
    background-image: linear-gradient(#063c63d0, #063c63d0), url("/kampus.jpg");
    background-position: center;
}
</style>