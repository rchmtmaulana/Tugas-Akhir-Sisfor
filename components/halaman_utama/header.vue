
<template>
   <header
      class="p-4 h-10 flex items-center fixed top-0 left-0 w-full z-20"
      style="background-color: rgb(28, 45, 93)"
    >
      <div class="tulisan text-white flex w-full mr-22"></div>
      <div
        class="flex text-white space-x-4 justify-center items-center"
        style="width: 450px"
      >
        <div class="flex space-x-4">
          <p>SITEMAP</p>
          <p>QUICK SITE</p>
        </div>
        <div class="flex space-x-2 items-center">
          <p class="text-white text-2sm">INA</p>
          <img src="/indonesia-flag.png" alt="indo" class="w-8 h-8" />
          <p class="text-white text-2sm">ENG</p>
          <img src="/english.png" alt="english" class="w-8 h-5" />
        </div>
      </div>
    </header>

  <header class = "pt-[40px] bg-navy fixed top-0 left-0 w-full flex items-center z-10">
    <div class = "container">
      <nav class="py-4 shadow-lg fixed left-0 w-full flex items-center" style="background-color: rgb(31, 52, 115);">
        <div class="flex ml-4">
            <img class="w-full" src="/unhas.png" alt="logo" style="width: 450px;" />
        </div>
        <ul>
          <li class="text-white font-bold text-base text-center px-2 flex">
            <p href="#" class="pl-2 pr-6 pt-1 hover:text-amber-600"><NuxtLink to="/">Beranda</NuxtLink></p>
            <p class="text-2xl">|</p>
            <div class=" navbar relative group pt-1">
                <a href="#" class="px-5 pt-1 hover:text-amber-600 group-hover:text">Profil</a>
                <div class="text-left absolute hidden text-white group-hover:block w-max px-5 py-2 rounded shadow-lg fixed" style="background-color: rgb(31, 52, 115)">
                    <ul class="py-2"><NuxtLink to="/profil/berita">Berita</NuxtLink></ul>
                    <ul class="py-2"><NuxtLink to="/profil/sejarah">Sejarah Singkat</NuxtLink></ul>
                    <ul class="py-2"><NuxtLink to="/profil/visimisi">Visi, Misi dan Sasaran</NuxtLink></ul>
                    <ul class="py-2"><NuxtLink to="/profil/manajemen">Manajemen</NuxtLink></ul>
                    <ul class="py-2"><NuxtLink to="/profil/struktur_organisasi">Struktur Organisasi</NuxtLink></ul>
                    <ul class="py-2"><NuxtLink to="/profil/master_plan">Master Plan</NuxtLink></ul>
                    <ul class="py-2"><NuxtLink to="/profil/peta_kampus">Peta Kampus</NuxtLink></ul>
                    <ul class="py-2"><NuxtLink to="/profil/mediatek">Mediatek</NuxtLink></ul>
                </div>
            </div>
            <p class="text-2xl">|</p>
            <div class="relative group pt-1">
                <a href="#" class="px-5 hover:text-amber-600 group-hover:text">Akademik</a>
                <div class="text-left absolute hidden text-white group-hover:block w-max px-5 py-2 rounded shadow-lg fixed" style="background-color: rgb(31, 52, 115)">
                    <ul class="py-2"><NuxtLink to="/akademik/departemen">Departemen</NuxtLink></ul>
                    <ul class="py-2"><NuxtLink to="/akademik/program_magister">Program Magister</NuxtLink></ul>
                    <ul class="py-2"><NuxtLink to="/akademik/program_doktor">Program Doktor</NuxtLink></ul>
                    <ul class="py-2"><NuxtLink to="/akademik/program_profesi">Program Profesi</NuxtLink></ul>
                    <ul class="py-2"><NuxtLink to="/akademik/akreditasi">Akreditasi</NuxtLink></ul>
                    <ul class="py-2"><NuxtLink to="/akademik/kalender_akademik">Kalender Akademik</NuxtLink></ul>
                </div>
            </div>
            <p class="text-2xl">|</p>
            <div class="relative group pt-1">
                <a href="#" class="px-5 hover:text-amber-600 group-hover:text">Sumber Daya</a>
                <div class="text-left absolute hidden text-white group-hover:block w-max px-5 py-2 rounded shadow-lg fixed" style="background-color: rgb(31, 52, 115)">
                    <ul class="py-2"><NuxtLink to="/sumberdaya/guru_besar">Guru Besar</NuxtLink></ul>
                    <ul class="py-2"><NuxtLink to="/sumberdaya/tenaga_kependidikan">Tenaga Kependidikan</NuxtLink></ul>
                    <ul class="py-2"><NuxtLink to="/sumberdaya/sarana_dan_prasarana">Sarana dan Prasarana</NuxtLink></ul>
                    <ul class="py-2"><NuxtLink to="/sumberdaya/perpustakaan">Perpustakaan</NuxtLink></ul>
                </div>
            </div>
            <p class="text-2xl">|</p>
            <div class="relative group pt-1">
                <a href="#" class="px-5 hover:text-amber-600 group-hover:text">K3</a>
                <div class="text-left absolute hidden text-white group-hover:block w-max px-5 py-2 rounded shadow-lg fixed" style="background-color: rgb(31, 52, 115)">
                    <ul class="py-2"><NuxtLink to="/K3/profil_k3">Profil K3</NuxtLink></ul>
                    <ul class="py-2"><NuxtLink to="/K3/struktur_organisasi">Struktur Organisasi K3</NuxtLink></ul>
                    <ul class="py-2"><NuxtLink to="/K3/tentang_k3">Tentang K3 FT-UH</NuxtLink></ul>
                    <ul class="py-2"><NuxtLink to="/K3/file_pendukung">File Pendukung</NuxtLink></ul>
                </div>
            </div>
            <p class="text-2xl">|</p>
            <div class="relative group pt-1">
                <a href="#" class="px-5 hover:text-amber-600 group-hover:text">Kemahasiswaan</a>
                <div class="text-left absolute hidden text-white group-hover:block w-max px-5 py-2 rounded shadow-lg fixed" style="background-color: rgb(31, 52, 115)">
                    <ul class="py-2"><NuxtLink to="/kemahasiswaan/upt_asrama">UPT Asrama (Ramtek)</NuxtLink></ul>
                    <ul class="py-2"><NuxtLink to="/kemahasiswaan/pengembangan_karakter_mahasiswa">Pengembangan Karakter Mahasiswa</NuxtLink></ul>
                    <ul class="py-2"><NuxtLink to="/kemahasiswaan/peningkatan_prestasi_mahasiswa">Peningkatan Prestasi Mahasiswa</NuxtLink></ul>
                    <ul class="py-2"><NuxtLink to="/kemahasiswaan/mahasiswa_inboundoutbound">Mahasiswa Inbound dan Outbound</NuxtLink></ul>
                    <ul class="py-2"><NuxtLink to="/kemahasiswaan/alumni">Alumni</NuxtLink></ul>
                    <ul class="py-2"><NuxtLink to="/kemahasiswaan/aturan_kemahasiswaan">Aturan Kemahasiswaan</NuxtLink></ul>
                    <ul class="py-2"><NuxtLink to="/kemahasiswaan/pengumuman">Pengumuman</NuxtLink></ul>
                </div>
            </div>
            <p class="text-2xl">|</p>
            <div class="relative group pt-1">
                <a href="#" class="px-5 hover:text-amber-600 group-hover:text">Riset dan Inovasi</a>
                <div class="text-left absolute hidden text-white group-hover:block w-max px-5 py-2 rounded shadow-lg fixed" style="background-color: rgb(31, 52, 115)">
                    <ul class="py-2"><NuxtLink to="/risetdaninovasi/daftar_penelitian_lbe">Daftar Penelitian LBE Tahun 2020</NuxtLink></ul>
                    <ul class="py-2"><NuxtLink to="/risetdaninovasi/hasil_inovasi">Hasil Inovasi</NuxtLink></ul>
                    <ul class="py-2"><NuxtLink to="/risetdaninovasi/hak_kekayaan_intelektual">Hak Kekayaan Intelektual</NuxtLink></ul>
                </div>
            </div>
            <p class="text-2xl">|</p>
            <div class="relative group pt-1">
                <a href="#" class="px-5 hover:text-amber-600 group-hover:text">Kemitraan</a>
                <div class="text-left absolute hidden text-white group-hover:block w-max px-5 py-2 rounded shadow-lg fixed" style="background-color: rgb(31, 52, 115)">
                    <ul class="py-2"><NuxtLink to="/kemitraan/kerjasama_dalam_negeri">Kerjasama Dalam Negeri</NuxtLink></ul>
                    <ul class="py-2"><NuxtLink to="/kemitraan/kerjasama_luar_negeri">Kerjasama Luar Negeri</NuxtLink></ul>
                </div>
            </div>
            <p class="text-2xl">|</p>
            <div class="relative group pt-1">
                <a href="#" class="px-5 hover:text-amber-600 group-hover:text">GPM-PR</a>
                <div class="text-left absolute hidden text-white group-hover:block w-max px-5 py-2 rounded shadow-lg fixed" style="background-color: rgb(31, 52, 115)">
                    <ul class="py-2"><NuxtLink to="/gpm-pr/profil_gpm-pr">Profil GPM-PR</NuxtLink></ul>
                    <ul class="py-2"><NuxtLink to="/gpm-pr/dokumen_mutu">Dokumen Mutu</NuxtLink></ul>
                    <ul class="py-2"><NuxtLink to="/gpm-pr/audit_mutu_akademik">Audit Mutu Akademik Internal</NuxtLink></ul>
                    <ul class="py-2"><NuxtLink to="/gpm-pr/akreditasi">Akreditasi</NuxtLink></ul>
                    <ul class="py-2"><NuxtLink to="/gpm-pr/LAM_teknik">LAM Teknik</NuxtLink></ul>
                    <ul class="py-2"><NuxtLink to="/gpm-pr/laporan_kepuasaan_pengguna">Laporan Kepuasan Pengguna</NuxtLink></ul>
                    <ul class="py-2"><NuxtLink to="/gpm-pr/survei_kepuasan_layanan_mahasiswa">Survei Kepuasan Layanan Mahasiswa</NuxtLink></ul>
                    <ul class="py-2"><NuxtLink to="/gpm-pr/galeri">Galeri</NuxtLink></ul>
                </div>
            </div>
            <p class="text-2xl">|</p>
            <div class="relative group pt-1">
                <a href="#" class="px-5 hover:text-amber-600 group-hover:text">COT</a>
                <div class="text-left absolute hidden text-white group-hover:block w-max px-5 py-2 rounded shadow-lg fixed" style="background-color: rgb(31, 52, 115)">
                    <ul class="py-2"><NuxtLink to="/cot/cot_website">COT Website</NuxtLink></ul>
                    <ul class="py-2"><NuxtLink to="/cot/jurnal_cot">Jurnal COT</NuxtLink></ul>
                    <ul class="py-2"><NuxtLink to="/cot/cot_newsletter">COT Newsletter</NuxtLink></ul>
                    <ul class="py-2"><NuxtLink to="/cot/U-I-G_collab">U-I-G Collaboration</NuxtLink></ul>
                </div>
            </div>
            <p class="text-2xl">|</p>
            <div class="relative group pt-1">
                <a href="#" class="px-5 hover:text-amber-600 group-hover:text">Dharma Wanita</a>
                <div class="text-left absolute hidden text-white group-hover:block w-max px-5 py-2 rounded shadow-lg fixed" style="background-color: rgb(31, 52, 115)">
                    <ul class="py-2"><NuxtLink to="/dharma_wanita/halaman_utama_dw">Halaman Utama Dharma Wanita</NuxtLink></ul>
                    <ul class="py-2"><NuxtLink to="/dharma_wanita/profil_dw">Profil Dharma Wanita</NuxtLink></ul>
                    <ul class="py-2"><NuxtLink to="/dharma_wanita/struktur_organisasi_dw">Struktur Organisasi Dharma Wanita</NuxtLink></ul>
                    <ul class="py-2"><NuxtLink to="/dharma_wanita/kegiatan_dw">Kegiatan Dharma Wanita</NuxtLink></ul>
                </div>
            </div>
          </li>
        </ul>
      </nav>
    </div>
  </header>
</template>

<style>

li {
  display: flex;
  align-items: center;
}

a {
  display: flex;
}
</style>