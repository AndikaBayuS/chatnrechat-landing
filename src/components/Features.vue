<template>
  <div class="container mx-auto py-16" id="features">
    <div class="mx-auto max-w-xl text-center antialiased" id="features">
      <p class="text-[14px] font-semibold text-[#0C1B4D]">
        NGGAK HARUS SIH SEBENERNYA
      </p>
      <p class="mt-3 text-3xl text-[#0C1B4D]">
        Kenapa Harus Pakai Chat N’ Rechat?
      </p>
      <p class="mt-2 text-[#0C1B4D]/60">
        Sebenernya yang bagus itu sih WhatsApp loh, mending pake WhatsApp aja
        deh. Yaudah berikut ini adalah fitur-fitur WhatsApp.
      </p>
    </div>

    <div class="mt-24 grid grid-cols-1 md:grid-cols-3">
      <div
        v-for="item in features"
        :key="item.title"
        class="flex justify-center text-center"
      >
        <div class="max-w-md">
          <img :src="item.src" class="mx-auto block max-h-[185px]" alt="" />
          <div class="p-6">
            <p
              class="mb-3 text-[18px] font-semibold text-[#0C1B4D] antialiased"
            >
              {{ item.title }}
            </p>
            <p class="text-[16px] text-[#0C1B4D]/60 antialiased">
              {{ item.desc }}
            </p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import features1 from "../assets/features/1.png";
import features2 from "../assets/features/2.png";
import features3 from "../assets/features/3.png";

const features = [
  {
    src: features1,
    title: "Groups to keep in touch",
    desc: "Keep in touch with the groups of people that matter the most, like your family or coworkers. With group chats, you can share messages, photos, and videos.",
  },
  {
    src: features2,
    title: "Simple, Reliable Messaging",
    desc: "Message your friends and family for free*. WhatsApp uses your phone's Internet connection to send messages so you can avoid SMS fees.",
  },
  {
    src: features3,
    title: "Speak Freely",
    desc: "With voice calls, you can talk to your friends and family for free*, even if they're in another country. And with free* video calls, you can have face-to-face conversations.",
  },
];
export default {
  setup() {
    return {
      features,
    };
  },
};
</script>

<style></style>
