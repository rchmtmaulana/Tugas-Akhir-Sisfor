<script setup>
import Header from "../components/halaman_utama/header.vue";
import Footer from "../components/halaman_utama/footer.vue";
import { ref, computed, onMounted } from 'vue';

const endpoint = "http://localhost:8055/items/Profil/1"
const sejarahData = ref([]);

async function getSejarah() {
  const api = await fetch(endpoint)
  const data = await api.json()
  console.log(data.data)
  sejarahData.value = data.data;
}

onMounted(() => {
  getSejarah();
})

const getImageUrl = (imageName) => {
  return `http://localhost:8055/assets/${imageName}`;
};
</script>

<template>
  <Header/>
  <div class="slug flex w-full text-white" style="height: 120px; margin-top: 130px; width: 100%;">
    <NuxtLink to="/">
      <img src="/home.png" alt="error" style="margin: 0px 0px 0px 210px; padding-top: 28px; width: 30px; height: 60px;" />
      <p style="margin: 0px 0px 0px 5px; padding-top: 30px; font-size: 20px; font-family: Times New Roman Thin;">Halaman</p>
    </NuxtLink>
    <p style="margin: 0px 0px 0px 5px; padding-top: 30px; font-size: 20px; font-family: Times New Roman Thin; display: flex"> > <span style="margin-left: 5px;" v-html="sejarahData.nama_halaman"></span></p>
  </div>
  <div Style="background-color: #d3d3dd">
      <section class="flex justify-center relative">
          <div class="content offside max-w-screen-xl w-full bg-white border rounded-xl overflow-hidden object-center" style=" margin-top: -30px; padding: 0px 200px 0px 200px;">
              <div class="flex justify-center mt-16"> 
                  <img :src="getImageUrl(sejarahData.gambar)" :alt="`sejarah ${sejarahData.id}`" class="w-full object-cover rounded-md object-center" style="height: 500px; width: 900px;">
              </div>
              <p class="text-lg" v-html="sejarahData.konten" style="font-size: 16px;"></p>
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