<script setup>
import Header from "../components/halaman_utama/header.vue";
import Footer from "../components/halaman_utama/footer.vue";
import { ref, computed, onMounted } from 'vue';

const endpoint = "http://localhost:8055/items/Berita"
const beritaData = ref([]);

const itemsPerPage = 6;
const currentPage = ref(1);

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

const paginatedBerita = computed(() => {
  const start = (currentPage.value - 1) * itemsPerPage;
  const end = start + itemsPerPage;
  return beritaData.value.slice(start, end);
});

const totalPages = computed(() => Math.ceil(beritaData.value.length / itemsPerPage));

function changePage(page) {
  currentPage.value = page;
}
</script>

<template>
    <Header/>
    <div class="slug w-full text-white" style="height: 120px; margin-top: 130px; width: 100%; display: flex;">
        <NuxtLink to="/profil/berita">
            <img src="/home.png" alt="error" class="" style="margin: 0px 0px 0px 210px; padding-top: 28px; width: 30px; height: 60px;" />
            <p style="margin: 0px 0px 0px 5px; padding-top: 30px; font-size: 20px; font-family: Times New Roman Thin;">Berita</p>
        </NuxtLink>
            <p style="margin: 0px 0px 0px 5px; padding-top: 30px; font-size: 20px; font-family: Times New Roman Thin;"> > nasional</p>
    </div>
    <div Style="background-color: #d3d3dd">
      <section class="flex justify-center relative" style="min-height: 850px">
        <div class="content offside max-w-screen-xl w-full bg-white border rounded-xl overflow-hidden" style="min-height: 900px; margin-top: -30px; position: relative;">
          <div class="pb-5">
            <h1 class="font-bold pt-5 text-center" style="font-family: Times New Roman Thin; font-size: 40px">Berita</h1>
          </div>
          <div class="grid grid-cols-3 gap-16 mt-8 mx-10">
            <div v-for="newsItem in paginatedBerita" :key="newsItem.id" class="flex flex-col items-center -my-4">
              <img :src="getImageUrl(newsItem.gambar)" alt="News Image" style="height: 200px;" class="w-full h-40 object-cover mb-2" />
              <h2 class="text-lg font-semibold" v-html="newsItem.judul" style="font-size: 15px;"></h2>
              <div class="flex items-center">
                <img src="/calendar.jpg" alt="error" class="w-4 h-4 mr-2" />
                <p class="text-sm text-grey">{{ newsItem.tanggal }}</p>
              </div>
            </div>
          </div>
          <div class="absolute bottom-0 left-1/2 transform -translate-x-1/2 mb-20">
            <button v-for="page in totalPages" :key="page" @click="changePage(page)" :class="{ 'bg-blue-500 text-white': currentPage === page, 'bg-gray-200': currentPage !== page }" class="mx-2 px-6 py-2 rounded cursor-pointer">
              {{ page }}
            </button>
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