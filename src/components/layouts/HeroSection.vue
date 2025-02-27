<script setup>
import Heroimg from "/heroimg.svg";
import BaseButton from "../ui/BaseButton.vue";
</script>

<template>
  <section class="w-full">
    <div>
      <div
        class="lg:py-6 mt-6 w-full flex-col md:flex-row flex justify-between"
      >
        <div class="text-center lg:text-left lg:w-1/2 w-full">
          <h1
            class="pt-4 text-[#191A23] font-bold text-4xl md:text-5xl lg:text-6xl"
          >
            Navigating the digital landscape for success
          </h1>
          <div
            class="text-[#000000] pt-8 text-center lg:text-left lg:max-w-[408px] px-6 lg:px-0"
          >
            <p>
              Our digital marketing agency helps businesses grow and succeed
              online through a range of services including SEO, PPC, social
              media marketing, and content creation.
            </p>
          </div>
          <div class="my-6 flex flex-col lg:block items-center justify-center">
            <BaseButton
              label="Book a consultation"
              class="lg:w-1/2 lg:m-0 m-4"
              variant="secondary"
            />
          </div>
        </div>
        <div>
          <img
            :src="Heroimg"
            class="lg:max-w-[600px] flex flex-col justify-center items-center lg:max-h-[515px] md:max-w-[300px]"
            alt="Logo"
          />
        </div>
      </div>
    </div>
  </section>
</template>
