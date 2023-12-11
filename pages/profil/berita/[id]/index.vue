<script setup>
import Header from "../components/halaman_utama/header.vue";
import Footer from "../components/halaman_utama/footer.vue";
import { ref, computed, onMounted } from 'vue';
import { useRoute } from 'vue-router';

const beritaData = ref([]);
const route = useRoute();

async function getBerita(id) {
  const endpoint = `http://localhost:8055/items/Berita/${id}`;
  const api = await fetch(endpoint);
  const data = await api.json();
  console.log(data.data);
  beritaData.value = data.data;
}

onMounted(() => {
  const id = route.params.id;
  getBerita(id);
});

const getImageUrl = (imageName) => {
  return `http://localhost:8055/assets/${imageName}`;
};
</script>

<template>
  <Header/>
  <div class="slug w-full text-white" style="height: 120px; margin-top: 130px; width: 100%; display: flex;">
        <NuxtLink to="/profil/berita">
            <img src="/home.png" alt="error" class="" style="margin: 0px 0px 0px 210px; padding-top: 28px; width: 30px; height: 60px;" />
            <p style="margin: 0px 0px 0px 5px; padding-top: 30px; font-size: 20px; font-family: Times New Roman Thin;">Berita</p>
        </NuxtLink>
        <p style="margin: 0px 0px 0px 5px; padding-top: 30px; font-size: 20px; font-family: Times New Roman Thin; display: flex"> > <span style="margin-left: 5px;" v-html="beritaData.judul"></span>
    </p>
    </div>
  <div  Style="background-color: #d3d3dd">
      <section class="flex justify-center relative" style="h">
          <div class="content offside max-w-screen-xl w-full bg-white border rounded-xl overflow-hidden object-center" style="margin-top: -30px;">
            <div style="padding: 0px 200px 0px 200px;">
              <img :src="getImageUrl(beritaData.gambar)" alt="News Image" style="height:500px; width:900px; margin-top: 50px;" class="w-full h-40 object-cover mb-2 mx-auto object-center" />
              <h1 class="text-lg font-semibold" v-html="beritaData.judul" style="font-size: 22px;"></h1>
              <div class="flex items-center">
                <img src="/calendar.jpg" alt="error" class="w-4 h-4 mr-2" />
                <p class="text-sm text-grey">{{ beritaData.tanggal }}</p>
              </div>
              <h1 class="text-lg" v-html="beritaData.konten" style="font-size: 16px;"></h1>
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