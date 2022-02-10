<template>
  <hr />
  <div class="container mx-auto py-16" id="teknologi">
    <div class="grid grid-cols-1 px-2 md:grid-cols-2 md:px-0">
      <div>
        <img src="../assets/phone2.png" alt="" />
      </div>
      <div>
        <p class="text-[14px] font-semibold text-[#0C1B4D]">
          TEKNOLOGI YANG DIGUNAKAN
        </p>
        <p class="mt-3 text-3xl text-[#0C1B4D]">
          Teknologi Yang Kami Gunakan Di Dalam Aplikasi Ini Akan Membuat DHH Dan
          Jason Fried Pensiun! 😱
        </p>
        <p class="mt-2 text-[#0C1B4D]/60">
          Lo bisa bayangin DHH sama Jason Fried aja jadi pensiun gegara aplikasi
          ini, apalagi lo yang cuma user dan beban kami, gegara lo pake dan
          daftar di aplikasi ini jadi kita harus bayar server DO tiap bulan,
          mana pas bayar harus tunjuk-tunjukan. Inilah alasan kenapa gak usah
          daftar:
        </p>

        <!-- The List -->
        <div class="mt-6">
          <div
            v-for="item in List"
            :key="item.title"
            class="mb-5 flex antialiased"
          >
            <div class="h-full rounded bg-[#0C1B4D]/10 py-4 px-4 text-3xl">
              {{ item.emoji }}
            </div>
            <div class="ml-5 block">
              <p class="text-lg font-semibold text-[#0C1B4D]">
                {{ item.title }}
              </p>
              <p class="text-[#0C1B4D]/60">
                {{ item.desc }}
              </p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
const List = [
  {
    emoji: "😠",
    title: "Kamu Adalah Beban Kami",
    desc: "Semakin banyak kamu yang mendaftar di aplikasi ini, artinya semakin banyak data yang perlu disimpan, nah kan jadi perlu server gede tuh. Makanya kamu beban!",
  },
  {
    emoji: "😴",
    title: "Males Buat Ngembangin",
    desc: "Lo bakal nemu bug, entah pesan yang mau dikirim gak bisa dikirim padahal lo belom pencet tombol enter atau masalah lainnya. Nah soal itu kita males buat benerin.",
  },
  {
    emoji: "🐨",
    title: "Pokoknya Males Aja Lah",
    desc: "Nggak tau lagi harus ngomong apa, pokoknya males aja sih kita bikin aplikasi chat kek gini. Makannya mending lo pake WhatsApp aja udah.",
  },
];
export default {
  setup() {
    return {
      List,
    };
  },
};
</script>

<style></style>
