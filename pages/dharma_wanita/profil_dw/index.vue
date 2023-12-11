<script setup>
import Header from "../components/halaman_utama/header.vue";
import Footer from "../components/halaman_utama/footer.vue";
import { ref, computed, onMounted } from 'vue';

const endpoint = "http://localhost:8055/items/DharmaWanita/3"
const strukturorganisasiData = ref([]);

async function getStrukturOrganisasi() {
  const api = await fetch(endpoint)
  const data = await api.json()
  console.log(data.data)
  strukturorganisasiData.value = data.data;
}

onMounted(() => {
    getStrukturOrganisasi();
})

const getImageUrl = (imageName) => {
  return `http://localhost:8055/assets/${imageName}`;
};
</script>

<template>
    <Header/>
    <div class="slug flex w-full text-white" style="height: 120px; margin-top: 130px; width: 100%;">
        <img src="/home.png" alt="error" class="" style="margin: 0px 0px 0px 210px; padding-top: 28px; width: 30px; height: 60px;" />
        <p style="margin: 0px 0px 0px 10px; padding-top: 30px; font-size: 20px; font-family: Times New Roman Thin;">Halaman > Profil Dharma Wanita</p>
    </div>
    <div  Style="background-color: #d3d3dd">
        <section class="flex justify-center relative" style="height: 700px">
            <div class="content offside max-w-screen-xl w-full bg-white border rounded-xl overflow-hidden" style="height: 750px; margin-top: -30px;">
                <div class="pb-5">
                    <h1 class="font-bold pt-5 text-center" style="font-family: Times New Roman Thin; font-size: 40px">Profil Dharma Wanita</h1>
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