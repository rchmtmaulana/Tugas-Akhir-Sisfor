<template>
  <section
    class="dharma-wanita warna justify-center px-52 pb-10"
    style="background-color: rgb(26, 46, 107)"
  >
    <div class="content w-full flex justify-around">
      <h1
        class="text-2xl pt-20 pb-12 text-center text-white"
        style="font-size: 40px; font-family: Times New Roman Thin"
      >
        Dharma Wanita
      </h1>
    </div>
    <div class="flex gap-8 w-full">
      <div class="" style="width: 1000px; height: 300px">
        <img
          src="/dharma-wanita.png"
          alt="Dharma Wanita"
          class="rounded-2xl w-full h-full"
        />
      </div>
      <div class="" style="width: 1700px; height: auto">
        <p
          class="text-white pt-16 text-justify"
          style="font-size: 25px; font-family: Roboto"
        >
          Dharma Wanita Persatuan Fakultas Teknik Unhas yang diketuai oleh Ny.
          Muralia Isran Ramli, aktif melakukan berbagai macam kegiatan seperti
          amaliah ramadhan, arisan di kapal, kegiatan BKMT dan DPW Unhas.
        </p>
      </div>
    </div>
    <div class="grid justify-items-end">
      <NuxtLink :to="{ name: 'utamadharmawanita'}"
        class="rounded-full py-[0.8rem] px-[2.5rem]"
        style="background-color: rgb(76, 89, 101); color: white"
      >
        SELENGKAPNYA
      </NuxtLink>
    </div>
  </section>
</template>
