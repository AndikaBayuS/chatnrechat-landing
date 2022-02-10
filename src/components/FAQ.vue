<template>
  <div class="container mx-auto max-w-screen-md py-16" id="faq">
    <div class="mx-auto max-w-xl text-center antialiased">
      <p class="text-[14px] font-semibold text-[#0C1B4D]">BANYAK YANG NANYA</p>
      <p class="mt-3 text-3xl text-[#0C1B4D]">
        Pertanyaan Yang Sering Ditanyain
      </p>
      <p class="mt-2 text-[#0C1B4D]/60">
        Sebenernya pertanyaan-pertanyaan ini kagak ada yang nanya sih, tapi ya
        ditaruh sini aja siapa tau lo mau baca ‘kan.
      </p>
    </div>
    <div class="mt-5">
      <Disclosure v-slot="{ open }" v-for="item in faq" :key="item.q">
        <DisclosureButton
          :class="open ? 'bg-[#4A72FF] text-white' : 'bg-none'"
          class="flex w-full justify-between rounded-t py-5 px-5 text-lg font-semibold text-[#0C1B4D]"
        >
          <span>{{ item.q }}</span>
          <ChevronDownIcon
            :class="open ? 'rotate-180 transform' : ''"
            class="h-5 w-5"
          />
        </DisclosureButton>
        <transition
          enter-active-class="transition duration-100 ease-out"
          enter-from-class="transform scale-95 opacity-0"
          enter-to-class="transform scale-100 opacity-100"
          leave-active-class="transition duration-75 ease-out"
          leave-from-class="transform scale-100 opacity-100"
          leave-to-class="transform scale-95 opacity-0"
        >
          <DisclosurePanel
            class="mb-5 rounded-b bg-[#4A72FF] py-5 px-5 text-white"
          >
            {{ item.a }}
          </DisclosurePanel>
        </transition>
        <hr class="px-5" />
      </Disclosure>
    </div>
  </div>
</template>

<script>
import { Disclosure, DisclosureButton, DisclosurePanel } from "@headlessui/vue";
import { ChevronDownIcon, ChevronUpIcon } from "@heroicons/vue/outline";

const faq = [
  { q: "Apakah aplikasi ini sudah dapat izin dari MUI?", a: "Aman 100% HALAL" },
  {
    q: "Apakah aplikasi ini gratis?",
    a: "Ya gratis dong, masa aplikasi chat aja berbayar sih. Lo kalo nanya yang bener dong. Bayangin aja kalo aplikasi ini berbayar, masa pas chat lo harus bayar setiap karakter. Kalo lo mau bayar mending pake MMS aja dah.",
  },
  {
    q: "Apakah data saya akan dijual ke agen khusus US?",
    a: "Emang ada yang mau beli data lo? elahhh",
  },
  {
    q: "Kenapa bumi muter? Apa karena di depan ada yang nikah?",
    a: "Kalo ada yang nikah apalagi mantan, yang ada perasaan lo yang muter muter",
  },
  {
    q: "Gimana caranya supaya si Rizal mau bikin konten buat Array ID?",
    a: "Gatau bang gw kan cuma nge coding desain yang lu bikin",
  },
  {
    q: "Pertanyaan di atas gabakal ada yang bisa jawab sih",
    a: "Iyain ae w mah bang",
  },
  {
    q: "Kenapa game **** burik, bang?",
    a: "Gaberani jawab gw, nama gamenya aja sampe gw sensor",
  },
];
export default {
  components: {
    Disclosure,
    DisclosureButton,
    DisclosurePanel,
    ChevronDownIcon,
    ChevronUpIcon,
  },
  setup() {
    return {
      faq,
    };
  },
};
</script>

<style></style>
