<template>
  <div class="min-h-screen bg-[#F8F7F4] font-body text-[#111]">

    <!-- ===== NAVBAR ===== -->
    <nav
      class="sticky top-0 z-50 bg-white border-b border-[#E5E2DC] px-5 lg:px-10 py-0 flex items-center justify-between h-16 shadow-[0_1px_0_#E5E2DC]">

      <!-- Logo + Brand -->
      <div class="flex items-center gap-3">
        <!-- Logo placeholder: ganti div ini dengan <img src="..." class="w-9 h-9 rounded-full object-cover"> -->
        <div
          class="w-9 h-9 rounded-full border-2 border-[#C8A96E] flex items-center justify-center overflow-hidden flex-shrink-0"
          title="Ganti dengan logo organisasi">
          <img src="../assets/img/bemumk.png" alt="Logo BEM" class="w-full h-full object-cover">
        </div>
        <div class="flex flex-col leading-tight">
          <span class="font-display font-bold text-[13px] tracking-[0.06em] uppercase text-[#111]">BEM UMK 2026</span>
          <span class="text-[10px] text-[#9B9286] tracking-wide font-medium">Kabinet Cakrawala Asa</span>
        </div>
      </div>

      <!-- Nav Links -->
      <div class="flex items-center gap-1">
        <button @click="currentPage = 'beranda'" :class="[
          'relative px-4 py-1.5 text-xs font-semibold tracking-wide rounded-md transition-all duration-200',
          currentPage === 'beranda'
            ? 'text-[#111] bg-[#F0EDE7]'
            : 'text-[#9B9286] hover:text-[#111] hover:bg-[#F0EDE7]'
        ]">
          Beranda
          <span v-if="currentPage === 'beranda'"
            class="absolute bottom-0 left-1/2 -translate-x-1/2 w-3 h-0.5 bg-[#C8A96E] rounded-full"></span>
        </button>
        <button @click="currentPage = 'jadwal'" :class="[
          'relative px-4 py-1.5 text-xs font-semibold tracking-wide rounded-md transition-all duration-200',
          currentPage === 'jadwal'
            ? 'text-[#111] bg-[#F0EDE7]'
            : 'text-[#9B9286] hover:text-[#111] hover:bg-[#F0EDE7]'
        ]">
          Jadwal Piket
          <span v-if="currentPage === 'jadwal'"
            class="absolute bottom-0 left-1/2 -translate-x-1/2 w-3 h-0.5 bg-[#C8A96E] rounded-full"></span>
        </button>
      </div>
    </nav>

    <!-- ===== BERANDA ===== -->
    <transition name="page">
      <div v-if="currentPage === 'beranda'" key="beranda">

        <!-- Hero -->
        <section class="relative bg-[#111] overflow-hidden">
          <!-- Subtle grid texture -->
          <div class="absolute inset-0 opacity-[0.04]"
            style="background-image: linear-gradient(#fff 1px, transparent 1px), linear-gradient(90deg, #fff 1px, transparent 1px); background-size: 48px 48px;">
          </div>
          <!-- Gold accent line -->
          <div
            class="absolute left-0 top-0 bottom-0 w-1 bg-gradient-to-b from-[#C8A96E]/0 via-[#C8A96E] to-[#C8A96E]/0">
          </div>

          <div class="relative z-10 max-w-4xl mx-auto px-6 lg:px-10 py-20 lg:py-28">
            <div class="flex items-center gap-2.5 mb-6">
              <div class="w-5 h-px bg-[#C8A96E]"></div>
              <span class="text-[#C8A96E] text-[10px] font-bold uppercase tracking-[0.2em]">Badan Eksekutif
                Mahasiswa</span>
            </div>
            <h1
              class="font-display text-4xl sm:text-5xl lg:text-6xl font-bold text-white leading-[1.08] tracking-tight mb-5">
              BEM UMK<br />
              <span class="text-[#C8A96E]">2026</span>
            </h1>
            <p class="text-white/50 text-sm leading-relaxed max-w-sm font-medium">
              Kabinet Cakrawala Asa - bersama membangun lingkungan akademik yang bersih, aktif, dan berdaya.
            </p>
          </div>
        </section>

        <!-- Foto Section -->
        <section class="max-w-4xl mx-auto px-5 lg:px-10 pt-14 pb-8">
          <div class="flex items-center justify-between mb-6">
            <div class="flex items-center gap-3">
              <div class="w-0.5 h-5 bg-[#C8A96E]"></div>
              <img src="../assets/img/fotoall.JPG" alt="Logo BEM" class="w-5 h-5 object-contain">
              <span class="text-xs font-bold uppercase tracking-[0.18em] text-[#9B9286]">Foto Bersama</span>
            </div>
            <span class="text-[10px] text-[#C2BDB5] tracking-wide">Pengurus 2024/2025</span>
          </div>

          <!-- Frame foto -->
          <div class="relative group rounded-xl overflow-hidden border border-[#E5E2DC] bg-white shadow-sm">
            <img src="../assets/img/fotoall.JPG" alt="Foto Bersama Pengurus" class="w-full aspect-[16/7] object-cover">


          </div>
        </section>

        <!-- Action Buttons -->
        <section class="max-w-4xl mx-auto px-5 lg:px-10 py-8">
          <div class="flex items-center gap-3 mb-6">
            <div class="w-0.5 h-5 bg-[#C8A96E]"></div>
            <span class="text-xs font-bold uppercase tracking-[0.18em] text-[#9B9286]">Menu Utama</span>
          </div>
          <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">

            <!-- Lihat Jadwal -->
            <button @click="currentPage = 'jadwal'"
              class="group flex items-center gap-4 p-5 bg-[#111] text-white rounded-xl border border-[#1E1E1E] hover:border-[#C8A96E]/60 transition-all duration-300 text-left shadow-sm hover:shadow-lg hover:shadow-black/10">
              <div
                class="w-10 h-10 rounded-lg bg-white/5 border border-white/10 flex items-center justify-center flex-shrink-0 group-hover:border-[#C8A96E]/40 transition-colors">
                <!-- Calendar icon (Heroicons) -->
                <svg class="w-5 h-5 text-[#C8A96E]" fill="none" viewBox="0 0 24 24" stroke="currentColor"
                  stroke-width="1.5">
                  <path stroke-linecap="round" stroke-linejoin="round"
                    d="M6.75 3v2.25M17.25 3v2.25M3 18.75V7.5a2.25 2.25 0 012.25-2.25h13.5A2.25 2.25 0 0121 7.5v11.25m-18 0A2.25 2.25 0 005.25 21h13.5A2.25 2.25 0 0021 18.75m-18 0v-7.5A2.25 2.25 0 015.25 9h13.5A2.25 2.25 0 0121 11.25v7.5" />
                </svg>
              </div>
              <div class="flex-1 min-w-0">
                <p class="font-semibold text-sm tracking-tight">Lihat Jadwal Piket</p>
                <p class="text-white/40 text-xs mt-0.5">Jadwal piket bulanan Maret–April</p>
              </div>
              <svg
                class="w-4 h-4 text-white/25 group-hover:text-[#C8A96E] group-hover:translate-x-0.5 transition-all duration-200 flex-shrink-0"
                fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
                <path stroke-linecap="round" stroke-linejoin="round" d="M8.25 4.5l7.5 7.5-7.5 7.5" />
              </svg>
            </button>

            <!-- Absensi -->
            <a href="https://forms.gle/YWsW9YmbeDuPDY2C6" target="_blank" rel="noopener noreferrer"
              class="group flex items-center gap-4 p-5 bg-white rounded-xl border border-[#E5E2DC] hover:border-[#C8A96E]/60 transition-all duration-300 shadow-sm hover:shadow-lg hover:shadow-black/5">
              <div
                class="w-10 h-10 rounded-lg bg-[#F8F7F4] border border-[#E5E2DC] flex items-center justify-center flex-shrink-0 group-hover:border-[#C8A96E]/40 transition-colors">
                <!-- ClipboardDocumentCheck icon (Heroicons) -->
                <svg class="w-5 h-5 text-[#C8A96E]" fill="none" viewBox="0 0 24 24" stroke="currentColor"
                  stroke-width="1.5">
                  <path stroke-linecap="round" stroke-linejoin="round"
                    d="M11.35 3.836c-.065.21-.1.433-.1.664 0 .414.336.75.75.75h4.5a.75.75 0 00.75-.75 2.25 2.25 0 00-.1-.664m-5.8 0A2.251 2.251 0 0113.5 2.25H15c1.012 0 1.867.668 2.15 1.586m-5.8 0c-.376.023-.75.05-1.124.08C9.095 4.01 8.25 4.973 8.25 6.108V8.25m8.9-4.414c.376.023.75.05 1.124.08 1.131.094 1.976 1.057 1.976 2.192V16.5A2.25 2.25 0 0118 18.75h-2.25m-7.5-10.5H4.875c-.621 0-1.125.504-1.125 1.125v11.25c0 .621.504 1.125 1.125 1.125h9.75c.621 0 1.125-.504 1.125-1.125V18.75m-7.5-10.5h6.375c.621 0 1.125.504 1.125 1.125v9.375m-8.25-3l1.5 1.5 3-3.75" />
                </svg>
              </div>
              <div class="flex-1 min-w-0">
                <p class="font-semibold text-sm tracking-tight text-[#111]">Absensi Piket</p>
                <p class="text-[#9B9286] text-xs mt-0.5">Isi form kehadiran via Google Forms</p>
              </div>
              <svg
                class="w-4 h-4 text-[#C2BDB5] group-hover:text-[#C8A96E] group-hover:translate-x-0.5 transition-all duration-200 flex-shrink-0"
                fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
                <path stroke-linecap="round" stroke-linejoin="round"
                  d="M13.5 6H5.25A2.25 2.25 0 003 8.25v10.5A2.25 2.25 0 005.25 21h10.5A2.25 2.25 0 0018 18.75V10.5m-10.5 6L21 3m0 0h-5.25M21 3v5.25" />
              </svg>
            </a>

          </div>
        </section>

        <!-- Info Cards -->
        <section class="max-w-4xl mx-auto px-5 lg:px-10 pb-16 grid grid-cols-1 sm:grid-cols-3 gap-3">
          <div v-for="info in infoCards" :key="info.title"
            class="bg-white rounded-xl border border-[#E5E2DC] p-5 flex gap-4 items-start">
            <div
              class="w-8 h-8 rounded-lg bg-[#F8F7F4] border border-[#E5E2DC] flex items-center justify-center flex-shrink-0 mt-0.5">
              <component :is="'svg'" class="w-4 h-4 text-[#C8A96E]" fill="none" viewBox="0 0 24 24"
                stroke="currentColor" stroke-width="1.5" v-html="info.icon"></component>
            </div>
            <div>
              <p class="text-xs font-bold text-[#111] mb-1">{{ info.title }}</p>
              <p class="text-[11px] text-[#9B9286] leading-relaxed">{{ info.desc }}</p>
            </div>
          </div>
        </section>

      </div>
    </transition>

    <!-- ===== JADWAL PIKET ===== -->
    <transition name="page">
      <div v-if="currentPage === 'jadwal'" key="jadwal">

        <!-- Hero Jadwal -->
        <section class="relative bg-[#111] overflow-hidden">
          <div class="absolute inset-0 opacity-[0.04]"
            style="background-image: linear-gradient(#fff 1px, transparent 1px), linear-gradient(90deg, #fff 1px, transparent 1px); background-size: 48px 48px;">
          </div>
          <div
            class="absolute left-0 top-0 bottom-0 w-1 bg-gradient-to-b from-[#C8A96E]/0 via-[#C8A96E] to-[#C8A96E]/0">
          </div>
          <div class="relative z-10 max-w-4xl mx-auto px-6 lg:px-10 py-16">
            <button @click="currentPage = 'beranda'"
              class="flex items-center gap-1.5 text-[#9B9286] hover:text-white text-xs font-semibold mb-8 transition-colors group">
              <svg class="w-3.5 h-3.5 group-hover:-translate-x-0.5 transition-transform" fill="none" viewBox="0 0 24 24"
                stroke="currentColor" stroke-width="2.5">
                <path stroke-linecap="round" stroke-linejoin="round" d="M15.75 19.5L8.25 12l7.5-7.5" />
              </svg>
              Kembali ke Beranda
            </button>
            <div class="flex items-center gap-2.5 mb-4">
              <div class="w-5 h-px bg-[#C8A96E]"></div>
              <span class="text-[#C8A96E] text-[10px] font-bold uppercase tracking-[0.2em]">Jadwal Kebersihan</span>
            </div>
            <h1 class="font-display text-3xl sm:text-4xl font-bold text-white tracking-tight">Jadwal Piket</h1>
            <p class="text-white/40 text-sm mt-2 font-medium">Periode Maret – April 2025</p>
          </div>
        </section>

        <!-- Tabel Jadwal -->
        <section class="max-w-4xl mx-auto px-5 lg:px-10 py-10 grid grid-cols-1 sm:grid-cols-2 gap-6">

          <!-- Maret -->
          <div class="bg-white rounded-xl border border-[#E5E2DC] overflow-hidden shadow-sm">
            <div class="flex items-center justify-between px-5 py-4 border-b border-[#E5E2DC] bg-[#F8F7F4]">
              <div class="flex items-center gap-3">
                <svg class="w-4 h-4 text-[#C8A96E]" fill="none" viewBox="0 0 24 24" stroke="currentColor"
                  stroke-width="1.5">
                  <path stroke-linecap="round" stroke-linejoin="round"
                    d="M6.75 3v2.25M17.25 3v2.25M3 18.75V7.5a2.25 2.25 0 012.25-2.25h13.5A2.25 2.25 0 0121 7.5v11.25m-18 0A2.25 2.25 0 005.25 21h13.5A2.25 2.25 0 0021 18.75m-18 0v-7.5A2.25 2.25 0 015.25 9h13.5A2.25 2.25 0 0121 11.25v7.5" />
                </svg>
                <span class="font-display font-bold text-sm tracking-tight text-[#111]">Maret</span>
              </div>
              <span class="text-[10px] text-[#C2BDB5] font-semibold uppercase tracking-widest">2025</span>
            </div>
            <div class="divide-y divide-[#F0EDE7]">
              <div v-for="(item, i) in jadwalMaret" :key="'m' + i"
                class="flex items-center gap-4 px-5 py-3.5 hover:bg-[#FDFCFB] transition-colors group">
                <div class="flex items-baseline gap-1 min-w-[52px]">
                  <span class="font-display font-bold text-xl text-[#111] leading-none">{{ i + 1 }}</span>
                  <span class="text-[9px] font-bold uppercase tracking-wider text-[#C2BDB5]">Mgg</span>
                </div>
                <div class="w-px h-6 bg-[#E5E2DC] flex-shrink-0"></div>
                <div
                  class="w-7 h-7 rounded-md bg-[#F8F7F4] border border-[#E5E2DC] flex items-center justify-center flex-shrink-0">
                  <component :is="'svg'" class="w-3.5 h-3.5 text-[#C8A96E]" fill="none" viewBox="0 0 24 24"
                    stroke="currentColor" stroke-width="1.5" v-html="item.icon"></component>
                </div>
                <span class="text-xs font-semibold text-[#333] leading-snug flex-1">{{ item.name }}</span>
              </div>
            </div>
          </div>

          <!-- April -->
          <div class="bg-white rounded-xl border border-[#E5E2DC] overflow-hidden shadow-sm">
            <div class="flex items-center justify-between px-5 py-4 border-b border-[#E5E2DC] bg-[#F8F7F4]">
              <div class="flex items-center gap-3">
                <svg class="w-4 h-4 text-[#C8A96E]" fill="none" viewBox="0 0 24 24" stroke="currentColor"
                  stroke-width="1.5">
                  <path stroke-linecap="round" stroke-linejoin="round"
                    d="M6.75 3v2.25M17.25 3v2.25M3 18.75V7.5a2.25 2.25 0 012.25-2.25h13.5A2.25 2.25 0 0121 7.5v11.25m-18 0A2.25 2.25 0 005.25 21h13.5A2.25 2.25 0 0021 18.75m-18 0v-7.5A2.25 2.25 0 015.25 9h13.5A2.25 2.25 0 0121 11.25v7.5" />
                </svg>
                <span class="font-display font-bold text-sm tracking-tight text-[#111]">April</span>
              </div>
              <span class="text-[10px] text-[#C2BDB5] font-semibold uppercase tracking-widest">2025</span>
            </div>
            <div class="divide-y divide-[#F0EDE7]">
              <div v-for="(item, i) in jadwalApril" :key="'a' + i"
                class="flex items-center gap-4 px-5 py-3.5 hover:bg-[#FDFCFB] transition-colors group">
                <div class="flex items-baseline gap-1 min-w-[52px]">
                  <span class="font-display font-bold text-xl text-[#111] leading-none">{{ i + 1 }}</span>
                  <span class="text-[9px] font-bold uppercase tracking-wider text-[#C2BDB5]">Mgg</span>
                </div>
                <div class="w-px h-6 bg-[#E5E2DC] flex-shrink-0"></div>
                <div
                  class="w-7 h-7 rounded-md bg-[#F8F7F4] border border-[#E5E2DC] flex items-center justify-center flex-shrink-0">
                  <component :is="'svg'" class="w-3.5 h-3.5 text-[#C8A96E]" fill="none" viewBox="0 0 24 24"
                    stroke="currentColor" stroke-width="1.5" v-html="item.icon"></component>
                </div>
                <span class="text-xs font-semibold text-[#333] leading-snug flex-1">{{ item.name }}</span>
              </div>
            </div>
          </div>

        </section>

        <!-- CTA Absensi -->
        <div class="max-w-4xl mx-auto px-5 lg:px-10 pb-16">
          <div
            class="bg-[#111] rounded-xl p-6 flex flex-col sm:flex-row items-start sm:items-center justify-between gap-5 border border-[#1E1E1E]">
            <div>
              <p class="text-white font-semibold text-sm">Sudah selesai piket?</p>
              <p class="text-white/40 text-xs mt-0.5">Catat kehadiranmu lewat form absensi resmi.</p>
            </div>
            <a href="https://forms.gle/YWsW9YmbeDuPDY2C6" target="_blank" rel="noopener noreferrer"
              class="flex items-center gap-2.5 px-5 py-2.5 bg-[#C8A96E] hover:bg-[#B8955A] text-[#111] text-xs font-bold rounded-lg transition-colors flex-shrink-0">
              <svg class="w-3.5 h-3.5" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
                <path stroke-linecap="round" stroke-linejoin="round"
                  d="M11.35 3.836c-.065.21-.1.433-.1.664 0 .414.336.75.75.75h4.5a.75.75 0 00.75-.75 2.25 2.25 0 00-.1-.664m-5.8 0A2.251 2.251 0 0113.5 2.25H15c1.012 0 1.867.668 2.15 1.586m-5.8 0c-.376.023-.75.05-1.124.08C9.095 4.01 8.25 4.973 8.25 6.108V8.25m8.9-4.414c.376.023.75.05 1.124.08 1.131.094 1.976 1.057 1.976 2.192V16.5A2.25 2.25 0 0118 18.75h-2.25m-7.5-10.5H4.875c-.621 0-1.125.504-1.125 1.125v11.25c0 .621.504 1.125 1.125 1.125h9.75c.621 0 1.125-.504 1.125-1.125V18.75m-7.5-10.5h6.375c.621 0 1.125.504 1.125 1.125v9.375m-8.25-3l1.5 1.5 3-3.75" />
              </svg>
              Isi Absensi Sekarang
            </a>
          </div>
        </div>

      </div>
    </transition>

    <!-- ===== FOOTER ===== -->
    <footer
      class="border-t border-[#E5E2DC] bg-white px-5 lg:px-10 py-5 flex flex-col sm:flex-row items-center justify-between gap-2">
      <div class="flex items-center gap-2">
        <div class="w-5 h-5 rounded-full bg-[#111] flex items-center justify-center">
          <svg class="w-2.5 h-2.5 text-[#C8A96E]" fill="none" viewBox="0 0 24 24" stroke="currentColor"
            stroke-width="1.5">
            <path stroke-linecap="round" stroke-linejoin="round"
              d="M12 3v1m0 16v1M4.22 4.22l.71.71m13.66 13.66.71.71M3 12H2m20 0h-1M4.22 19.78l.71-.71M18.36 5.64l.71-.71M12 7a5 5 0 100 10A5 5 0 0012 7z" />
          </svg>
        </div>
        <span class="text-xs font-semibold text-[#111] tracking-tight">BEM UMK 2026</span>
        <span class="text-[10px] text-[#C2BDB5] hidden sm:inline">· Kabinet Cakrawala Asa</span>
      </div>
      <p class="text-[10px] text-[#C2BDB5] tracking-wide">© 2025 · Semua hak dilindungi</p>
    </footer>

  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue'

interface JadwalItem {
  name: string
  icon: string
}

interface InfoCard {
  title: string
  desc: string
  icon: string
}

export default defineComponent({
  name: 'App',
  setup() {
    const currentPage = ref<string>('beranda')

    // SVG path snippets (Heroicons) for v-html
    const iconBroom = `<path stroke-linecap="round" stroke-linejoin="round" d="M12 6.75a.75.75 0 110-1.5.75.75 0 010 1.5zM12 12.75a.75.75 0 110-1.5.75.75 0 010 1.5zM12 18.75a.75.75 0 110-1.5.75.75 0 010 1.5z"/>`
    const iconStar = `<path stroke-linecap="round" stroke-linejoin="round" d="M11.48 3.499a.562.562 0 011.04 0l2.125 5.111a.563.563 0 00.475.345l5.518.442c.499.04.701.663.321.988l-4.204 3.602a.563.563 0 00-.182.557l1.285 5.385a.562.562 0 01-.84.61l-4.725-2.885a.563.563 0 00-.586 0L6.982 20.54a.562.562 0 01-.84-.61l1.285-5.386a.562.562 0 00-.182-.557l-4.204-3.602a.563.563 0 01.321-.988l5.518-.442a.563.563 0 00.475-.345L11.48 3.5z"/>`
    const iconUsers = `<path stroke-linecap="round" stroke-linejoin="round" d="M15 19.128a9.38 9.38 0 002.625.372 9.337 9.337 0 004.121-.952 4.125 4.125 0 00-7.533-2.493M15 19.128v-.003c0-1.113-.285-2.16-.786-3.07M15 19.128v.106A12.318 12.318 0 018.624 21c-2.331 0-4.512-.645-6.374-1.766l-.001-.109a6.375 6.375 0 0111.964-3.07M12 6.375a3.375 3.375 0 11-6.75 0 3.375 3.375 0 016.75 0zm8.25 2.25a2.625 2.625 0 11-5.25 0 2.625 2.625 0 015.25 0z"/>`
    const iconGlobe = `<path stroke-linecap="round" stroke-linejoin="round" d="M12 21a9.004 9.004 0 008.716-6.747M12 21a9.004 9.004 0 01-8.716-6.747M12 21c2.485 0 4.5-4.03 4.5-9S14.485 3 12 3m0 18c-2.485 0-4.5-4.03-4.5-9S9.515 3 12 3m0 0a8.997 8.997 0 017.843 4.582M12 3a8.997 8.997 0 00-7.843 4.582m15.686 0A11.953 11.953 0 0112 10.5c-2.998 0-5.74-1.1-7.843-2.918m15.686 0A8.959 8.959 0 0121 12c0 .778-.099 1.533-.284 2.253m0 0A17.919 17.919 0 0112 16.5c-3.162 0-6.133-.815-8.716-2.247m0 0A9.015 9.015 0 013 12c0-1.605.42-3.113 1.157-4.418"/>`
    const iconBriefcase = `<path stroke-linecap="round" stroke-linejoin="round" d="M20.25 14.15v4.25c0 1.094-.787 2.036-1.872 2.18-2.087.277-4.216.42-6.378.42s-4.291-.143-6.378-.42c-1.085-.144-1.872-1.086-1.872-2.18v-4.25m16.5 0a2.18 2.18 0 00.75-1.661V8.706c0-1.081-.768-2.015-1.837-2.175a48.114 48.114 0 00-3.413-.387m4.5 8.006c-.194.165-.42.295-.673.38A23.978 23.978 0 0112 15.75c-2.648 0-5.195-.429-7.577-1.22a2.016 2.016 0 01-.673-.38m0 0A2.18 2.18 0 013 12.489V8.706c0-1.081.768-2.015 1.837-2.175a48.111 48.111 0 013.413-.387m7.5 0V5.25A2.25 2.25 0 0013.5 3h-3a2.25 2.25 0 00-2.25 2.25v.894m7.5 0a48.667 48.667 0 00-7.5 0M12 12.75h.008v.008H12v-.008z"/>`
    const iconScale = `<path stroke-linecap="round" stroke-linejoin="round" d="M12 3v17.25m0 0c-1.472 0-2.882.265-4.185.75M12 20.25c1.472 0 2.882.265 4.185.75M18.75 4.97A48.416 48.416 0 0012 4.5c-2.291 0-4.545.16-6.75.47m13.5 0c1.01.143 2.01.317 3 .52m-3-.52l2.62 10.726c.122.499-.106 1.028-.589 1.202a5.988 5.988 0 01-2.031.352 5.988 5.988 0 01-2.031-.352c-.483-.174-.711-.703-.59-1.202L18.75 4.97zm-16.5.52c.99-.203 1.99-.377 3-.52m0 0l2.62 10.726c.122.499-.106 1.028-.589 1.202a5.989 5.989 0 01-2.031.352 5.989 5.989 0 01-2.031-.352c-.483-.174-.711-.703-.59-1.202L5.25 5.49z"/>`
    const iconBeaker = `<path stroke-linecap="round" stroke-linejoin="round" d="M9.75 3.104v5.714a2.25 2.25 0 01-.659 1.591L5 14.5M9.75 3.104c-.251.023-.501.05-.75.082m.75-.082a24.301 24.301 0 014.5 0m0 0v5.714c0 .597.237 1.17.659 1.591L19.8 15.3M14.25 3.104c.251.023.501.05.75.082M19.8 15.3l-1.57.393A9.065 9.065 0 0112 15a9.065 9.065 0 00-6.23-.693L5 14.5m14.8.8l1.402 1.402c1 1 .03 2.798-1.338 2.798a5.554 5.554 0 01-3.867-1.625l-.844-.844a5.553 5.553 0 00-3.644-1.635h-.074a5.554 5.554 0 00-3.645 1.635l-.844.844A5.554 5.554 0 013.338 19.5C1.97 19.5 1 17.702 2 16.702L3.4 15.3"/>`
    const iconSignal = `<path stroke-linecap="round" stroke-linejoin="round" d="M9.348 14.651a3.75 3.75 0 010-5.303m5.304-.001a3.75 3.75 0 010 5.304m-7.425 2.122a6.75 6.75 0 010-9.546m9.546.001a6.75 6.75 0 010 9.545M5.106 18.894c-3.808-3.808-3.808-9.98 0-13.789m13.788 0c3.808 3.808 3.808 9.981 0 13.79M12 12h.008v.008H12V12z"/>`
    const iconHeart = `<path stroke-linecap="round" stroke-linejoin="round" d="M21 8.25c0-2.485-2.099-4.5-4.688-4.5-1.935 0-3.597 1.126-4.312 2.733-.715-1.607-2.377-2.733-4.313-2.733C5.1 3.75 3 5.765 3 8.25c0 7.22 9 12 9 12s9-4.78 9-12z"/>`

    const jadwalMaret: JadwalItem[] = [
      { name: 'BPH', icon: iconStar },
      { name: 'Kementrian Dalam Negeri', icon: iconBriefcase },
      { name: 'Kementrian Luar Negeri', icon: iconGlobe },
      { name: 'Kementrian PSDM', icon: iconUsers },
    ]

    const jadwalApril: JadwalItem[] = [
      { name: 'Kementrian Advokastrat', icon: iconScale },
      { name: 'Kementrian Riset', icon: iconBeaker },
      { name: 'Kementrian Kominfo', icon: iconSignal },
      { name: 'Kementrian Sosial', icon: iconHeart },
    ]

    const infoCards: InfoCard[] = [
      {
        title: 'Piket Rutin',
        desc: 'Dilaksanakan setiap minggu sesuai jadwal yang telah ditetapkan.',
        icon: `<path stroke-linecap="round" stroke-linejoin="round" d="M6.75 3v2.25M17.25 3v2.25M3 18.75V7.5a2.25 2.25 0 012.25-2.25h13.5A2.25 2.25 0 0121 7.5v11.25m-18 0A2.25 2.25 0 005.25 21h13.5A2.25 2.25 0 0021 18.75m-18 0v-7.5A2.25 2.25 0 015.25 9h13.5A2.25 2.25 0 0121 11.25v7.5"/>`
      },
      {
        title: 'Absensi Wajib',
        desc: 'Setiap anggota wajib mengisi form absensi setelah piket selesai.',
        icon: `<path stroke-linecap="round" stroke-linejoin="round" d="M9 12.75L11.25 15 15 9.75M21 12a9 9 0 11-18 0 9 9 0 0118 0z"/>`
      },
      {
        title: 'Tanggung Jawab Bersama',
        desc: 'Piket adalah kewajiban kolektif demi lingkungan yang nyaman.',
        icon: `<path stroke-linecap="round" stroke-linejoin="round" d="M15 19.128a9.38 9.38 0 002.625.372 9.337 9.337 0 004.121-.952 4.125 4.125 0 00-7.533-2.493M15 19.128v-.003c0-1.113-.285-2.16-.786-3.07M15 19.128v.106A12.318 12.318 0 018.624 21c-2.331 0-4.512-.645-6.374-1.766l-.001-.109a6.375 6.375 0 0111.964-3.07M12 6.375a3.375 3.375 0 11-6.75 0 3.375 3.375 0 016.75 0zm8.25 2.25a2.625 2.625 0 11-5.25 0 2.625 2.625 0 015.25 0z"/>`
      },
    ]

    return { currentPage, jadwalMaret, jadwalApril, infoCards }
  }
})
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=DM+Sans:wght@400;500;600;700&family=DM+Serif+Display&display=swap');

body {
  font-family: 'DM Sans', sans-serif;
}

.font-body {
  font-family: 'DM Sans', sans-serif;
}

.font-display {
  font-family: 'DM Serif Display', serif;
}

.page-enter-active,
.page-leave-active {
  transition: opacity 0.25s ease, transform 0.25s ease;
}

.page-enter-from {
  opacity: 0;
  transform: translateY(8px);
}

.page-leave-to {
  opacity: 0;
  transform: translateY(-4px);
}
</style>