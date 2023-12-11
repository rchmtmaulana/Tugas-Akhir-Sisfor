<script setup>
import Header from "../components/halaman_utama/header.vue";
import Footer from "../components/halaman_utama/footer.vue";

const endpoint = "http://localhost:8055/items/DharmaWanita/2"
const endpoint2 = "http://localhost:8055/items/GaleriDharmaWanita"
const endpoint3 = "http://localhost:8055/items/Berita/14"

const dharmawanitaData = ref([]);
const galeridwData = ref([]);
const beritadwData = ref([]);

async function getdharmawanita() {
  const api = await fetch(endpoint)
  const data = await api.json()
  console.log(data.data)
  dharmawanitaData.value = data.data;
}

async function getGaleridw() {
  const api = await fetch(endpoint2)
  const data = await api.json()
  console.log(data.data)
  galeridwData.value = data.data;
}

async function getberitadwData() {
  const api = await fetch(endpoint3)
  const data = await api.json()
  console.log(data.data)
  beritadwDataData.value = data.data;
}

onMounted(() => {
  getdharmawanita();
  getGaleridw();
  getberitadwData();
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
        <p style="margin: 0px 0px 0px 5px; padding-top: 30px; font-size: 20px; font-family: Times New Roman Thin; display: flex"> > <span style="margin-left: 5px;" v-html="dharmawanitaData.nama_halaman"></span></p>
    </div>
    <div  Style="background-color: #d3d3dd">
        <section class="flex justify-center relative">
            <div class="content offside max-w-screen-xl w-full bg-white border rounded-xl overflow-hidden flex flex-col items-center  " style=" margin-top: -30px; padding: 40px 0px 0px 0px;">
                <p class="text-lg " v-html="dharmawanitaData.konten"></p>
                <div class="grid grid-cols-3 gap-8 items-center text-center" style="margin: 0px 50px 0px 50px;">
                    <div v-for="galeridw in galeridwData" :key="galeridwData.id" class="text-center">
                        <img :src="getImageUrl(galeridw.gambar)" alt="News Image" style="height: 200px;" class="w-full h-40 object-cover mb-0" />
                        <h2 class="text-lg font-semibold " v-html="galeridw.judul" style="font-size: 15px;"></h2>
                    </div>
                </div>
                <div class="text-center mt-14 mb-14">
                    <h2 class="text-lg font-bold" style="font-size: 24px;">BERITA DHARMA WANITA</h2>
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