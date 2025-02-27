<script>
import Amazon from "../../assets/amazon.svg";
import Dribble from "../../assets/dribble.svg";
import Hubspot from "../../assets/hubspot.png";
import Netflix from "../../assets/netflix.svg";
import Zoom from "../../assets/zoom.svg";

const logos = [Amazon, Dribble, Hubspot, Netflix, Zoom];
</script>
<template>
  <div class="flex flex-row border p-4 items-center justify-center flex-wrap">
    <img
      v-for="(logo, index) in logos"
      :key="index"
      :src="logo"
      alt="Company Logo"
      class="w-[100px] h-auto rounded-lg shadow-md"
    />
  </div>
</template>
