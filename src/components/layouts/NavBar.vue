<script setup>
import logo from "/logo.svg";
import BaseButton from "../ui/BaseButton.vue";
import { ref } from "vue";
const Menu = ref([
  { name: "About Us", href: "#about" },
  { name: "Services", href: "#services" },
  { name: "Use Cases", href: "#useCases" },
  { name: "Pricing", href: "#pricing" },
  { name: "Blog", href: "#blog" },
]);

const isMenuOpen = ref(false);
</script>

<template lang="">
  <header
    class="flex justify-between items-center p-6 bg-opacity-50 relative z-20"
  >
    <div class="flex justify-center items-center">
      <img :src="logo" class="w-16 md:w-24 lg:w-32 xl:w-40 h-auto" alt="Logo" />
    </div>
    <!-- Mobile Toggle Button -->
    <div class="md:hidden z-30">
      <button
        type="button"
        class="block focus:outline-none"
        @click="isMenuOpen = !isMenuOpen"
      >
        <span v-if="isMenuOpen" class="text-5xl">
          <img
            src="https://img.icons8.com/ios-filled/100/00000/delete-sign.png"
            alt="close"
            width="30"
            height="30"
          />
        </span>
        <span v-else class="text-5xl">
          <img
            src="https://img.icons8.com/ios-filled/100/000000/menu--v6.png"
            alt="menu"
            width="30"
            height="30"
          />
        </span>
      </button>
    </div>
    <!-- Navbar Link -->
    <nav
      :class="[
        'fixed inset-0 z-20 flex flex-col items-center justify-center bg-[#ffff] md:relative md:bg-transparent md:flex md:justify-between md:flex-row',
        isMenuOpen ? 'block' : 'hidden',
      ]"
    >
      <ul
        class="flex flex-col items-center space-y-5 md:flex-row md:space-x-5 md:space-y-0"
      >
        <li v-for="item in Menu" :key="item.name">
          <a
            :href="item.href"
            class="block text-black transition hover:text-primary ease-linear text-xl md:text-lg"
            @click="scrollToSection(item.href)"
          >
            <p>{{ item.name }}</p>
          </a>
        </li>
        <BaseButton label="Request a quote" variant="outline" />
      </ul>
    </nav>
  </header>
</template>
