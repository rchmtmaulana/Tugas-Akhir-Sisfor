<script setup>
import Header from "../components/halaman_utama/header.vue";
import Footer from "../components/halaman_utama/footer.vue";
import { ref, computed, onMounted } from 'vue';

const endpoint = "http://localhost:8055/items/Profil/6"
const petaData = ref([]);

async function getPeta() {
  const api = await fetch(endpoint)
  const data = await api.json()
  console.log(data.data)
  petaData.value = data.data;
}

onMounted(() => {
  getPeta();
})
</script>

<template>
    <Header/>
    <div class="slug flex w-full text-white" style="height: 120px; margin-top: 130px; width: 100%;">
        <img src="/home.png" alt="error" class="" style="margin: 0px 0px 0px 210px; padding-top: 28px; width: 30px; height: 60px;" />
        <p style="margin: 0px 0px 0px 10px; padding-top: 30px; font-size: 20px; font-family: Times New Roman Thin;">Profil > {{ petaData.nama_halaman }}</p>
    </div>
    <div  Style="background-color: #d3d3dd">
        <section class="flex justify-center relative" style="height: 200px" >
            <div class="content offside max-w-screen-xl w-full bg-white border rounded-xl overflow-hidden" style=" height: 250px;  margin-top: -30px; padding: 0px 150px 0px 150px;">
                <p class="text-lg" v-html="petaData.konten" style="font-size: 16px;"></p>
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