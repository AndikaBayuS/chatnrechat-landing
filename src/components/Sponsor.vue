<template>
  <div class="container mx-auto mt-5 h-full md:h-32">
    <div class="h-full w-full rounded-md bg-[#4A72FF]/5">
      <div
        class="flex h-full flex-col items-center justify-between px-5 md:flex-row"
      >
        <img
          v-for="item in sponsor"
          :key="item.src"
          :src="item.src"
          class="py-5"
        />
      </div>
    </div>
  </div>
</template>

<script>

import sponsor1 from "../assets/sponsor/1.png";
import sponsor2 from "../assets/sponsor/2.png";
import sponsor3 from "../assets/sponsor/3.png";
import sponsor4 from "../assets/sponsor/4.png";
import sponsor5 from "../assets/sponsor/5.png";

const sponsor = [
  { src: sponsor1 },
  { src: sponsor2 },
  { src: sponsor3 },
  { src: sponsor4 },
  { src: sponsor5 },
];

export default {
  setup() {
    return {
      sponsor,
    };
  },
};
</script>

<style></style>
