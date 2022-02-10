<template>
  <Popover as="nav" class="container mx-auto bg-[#EEF2FF]" v-slot="{ open }">
    <div class="border-b border-white/20 px-2 sm:px-0">
      <div class="relative flex h-16 items-center justify-between">
        <div class="absolute inset-y-0 left-0 flex items-center sm:hidden">
          <!-- Mobile menu button-->
          <PopoverButton
            class="inline-flex items-center justify-center rounded-md p-2 text-gray-400 hover:bg-[#4A72FF] hover:text-white focus:outline-none focus:ring-2 focus:ring-inset focus:ring-white"
          >
            <span class="sr-only">Open main menu</span>
            <MenuIcon v-if="!open" class="block h-6 w-6" aria-hidden="true" />
            <XIcon v-else class="block h-6 w-6" aria-hidden="true" />
          </PopoverButton>
        </div>
        <!-- Nav Menu -->
        <div class="flex flex-1 items-center sm:items-stretch">
          <div
            class="flex flex-1 flex-shrink-0 items-center justify-center sm:justify-start"
          >
            <img
              class="block h-8 w-auto lg:hidden"
              src="../assets/hello.png"
              alt="Workflow"
            />
            <img
              class="hidden h-8 w-auto lg:block"
              src="../assets/hello.png"
              alt="Workflow"
            />
          </div>
          <div class="hidden sm:ml-6 sm:block">
            <div class="space-x-4r flex flex-1 justify-center">
              <a
                v-for="item in navigation"
                :key="item.name"
                :href="item.href"
                :class="[
                  item.current
                    ? 'font-semibold text-[#0C1B4D]'
                    : 'text-[#0C1B4D] hover:font-semibold',
                  'px-3 py-2 text-[16px]',
                ]"
                :aria-current="item.current ? 'page' : undefined"
                >{{ item.name }}</a
              >
            </div>
          </div>
          <div class="hidden flex-1 items-center justify-end sm:flex">
            <button
              class="rounded bg-[#4A72FF] py-2 px-4 text-white shadow-xl shadow-[#4A72FF]/25"
            >
              Download
            </button>
          </div>
        </div>
        <!-- End of Nav Menu -->
      </div>
    </div>

    <!-- Mobile Menu -->
    <transition
      enter-active-class="duration-200 ease-out"
      enter-from-class="opacity-0 scale-95"
      enter-to-class="opacity-100 scale-100"
      leave-active-class="duration-100 ease-in"
      leave-from-class="opacity-100 scale-100"
      leave-to-class="opacity-0 scale-95"
    >
      <PopoverPanel
        focus
        class="absolute inset-x-0 top-0 origin-top-right transform p-2 transition md:hidden"
      >
        <div
          class="divide-y-2 divide-gray-50 rounded-lg bg-white shadow-lg ring-1 ring-black ring-opacity-5"
        >
          <div class="px-5 pt-5 pb-6">
            <div class="flex items-center justify-between">
              <div class="-mr-2">
                <PopoverButton
                  class="inline-flex items-center justify-center rounded-md bg-white p-2 text-gray-400 hover:bg-gray-100 hover:text-gray-500 focus:outline-none focus:ring-2 focus:ring-inset focus:ring-indigo-500"
                >
                  <span class="sr-only">Close menu</span>
                  <XIcon class="h-6 w-6" aria-hidden="true" />
                </PopoverButton>
              </div>
            </div>
            <div class="mt-6">
              <nav class="grid gap-y-8">
                <a
                  v-for="item in navigation"
                  :key="item.name"
                  :href="item.href"
                  class="-m-3 flex items-center rounded-md p-3 hover:bg-gray-50"
                >
                  <component
                    :is="item.icon"
                    class="h-6 w-6 flex-shrink-0 text-indigo-600"
                    aria-hidden="true"
                  />
                  <span class="ml-3 text-base font-medium text-gray-900">
                    {{ item.name }}
                  </span>
                </a>
              </nav>
            </div>
          </div>
        </div>
      </PopoverPanel>
    </transition>
    <!-- End of Mobile Menu -->

    <!-- Header/Hero -->
    <div class="container mx-auto mt-6 px-2 sm:py-16 sm:px-0">
      <div class="grid grid-cols-1 sm:grid-cols-2">
        <section>
          <div class="antialised tracking-tigh w-full md:w-4/5">
            <p class="text-[14px] font-semibold text-[#4A72FF]">
              CHAT N’ RECHAT
            </p>
            <p class="text-[34px] leading-[44.27px] text-[#0C1B4D]">
              Sebuah aplikasi chatting yang bisa bikin kamu lupa diri, tapi
              tidak lupa jasa pahlawan!
            </p>
            <p class="mt-3 mb-5 text-[18px] leading-[30px] text-[#0C1B4D]/60">
              Sebenernya banyak banget aplikasi chatting yang lebih bagus dari
              ini, maka dari itu lebih baik pake yang lain aja deh ya daripada
              pake aplikasi yang ini.
            </p>
          </div>
          <div class="flex flex-col md:flex-row">
            <button
              class="mr-3 mb-3 w-full rounded bg-[#4A72FF] py-3 px-12 text-white sm:w-auto md:mb-0 md:shadow-xl md:shadow-[#4A72FF]/25"
            >
              Register
              <span
                ><ArrowCircleRightIcon class="ml-2 inline-block h-6 w-6"
              /></span>
            </button>
            <button
              class="w-full rounded bg-[#4A72FF]/5 py-3 px-12 text-[#4A72FF] sm:w-auto"
            >
              Learn More
            </button>
          </div>

          <!-- Count -->
          <div
            class="mx-auto mt-10 grid max-w-md grid-cols-2 divide-x-2 md:mx-0"
          >
            <div class="flex">
              <div class="h-full">
                <DownloadIcon
                  class="mr-5 inline-block h-6 w-6 text-[#0C1B4D99]"
                />
              </div>
              <div class="block">
                <p class="text-[#0C1B4D99]">TOTAL DON’TLOUD</p>
                <p class="text-[24px] font-semibold text-[#0C1B4D]">
                  1,501,234
                </p>
              </div>
            </div>

            <div class="flex">
              <div class="ml-5">
                <UserIcon class="mr-3 inline-block h-6 w-6 text-[#0C1B4D99]" />
              </div>
              <div class="block">
                <p class="text-[#0C1B4D99]">TOTAL USERS</p>
                <p class="text-center text-[24px] font-semibold text-[#0C1B4D]">
                  1,318,829
                </p>
              </div>
            </div>
          </div>
          <!-- End of Count -->
        </section>

        <section class="mt-12 sm:mt-0">
          <img src="../assets/phone.png" alt="" />
        </section>
      </div>
    </div>
    <!-- End of Header/Hero -->
  </Popover>
</template>

<script>
import {
  Popover,
  PopoverButton,
  PopoverGroup,
  PopoverPanel,
  Menu,
  MenuButton,
  MenuItem,
  MenuItems,
} from "@headlessui/vue";
import {
  BellIcon,
  MenuIcon,
  XIcon,
  ArrowCircleRightIcon,
  DownloadIcon,
  UserIcon,
} from "@heroicons/vue/outline";

const navigation = [
  { name: "Beranda", href: "#", current: true },
  { name: "Fitur-fitur", href: "#features", current: false },
  { name: "Teknologi", href: "#teknologi", current: false },
  { name: "FAQ", href: "#faq", current: false },
];

export default {
  components: {
    Menu,
    MenuButton,
    MenuItem,
    MenuItems,
    Popover,
    PopoverButton,
    PopoverGroup,
    PopoverPanel,
    BellIcon,
    MenuIcon,
    XIcon,
    ArrowCircleRightIcon,
    DownloadIcon,
    UserIcon,
  },
  setup() {
    return {
      navigation,
    };
  },
};
</script>
