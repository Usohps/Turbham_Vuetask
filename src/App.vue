<template>
  <div class="bg-white min-h-screen">
    <!-- Wrap components in Suspense to handle loading -->
    <Suspense>
      <template #default>
        <!-- Wrap all Components inside a single root element -->
        <div class="lg:px-24">
          <NavBar />
          <HeroSection />
        </div>
      </template>
      <template #fallback>
        <div class="flex justify-center items-center min-h-screen">
          <LoadingSpinner />
        </div>
      </template>
    </Suspense>
  </div>
</template>

<script setup>
import { defineAsyncComponent } from "vue";
//Import Components Asynchronously
const NavBar = defineAsyncComponent(() =>
  import("./components/layouts/NavBar.vue")
);
const HeroSection = defineAsyncComponent(() =>
  import("./components/layouts/HeroSection.vue")
);

import LoadingSpinner from "./components/ui/LoadingSpinner.vue";
</script>
