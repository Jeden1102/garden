<template>
  <div class="pt-16">
    <UiCard>
      <NuxtImg
        :src="imageSrc"
        alt="Product image"
        class="-mt-16 h-52 w-fit mx-auto md:h-72"
      />
      <div :class="cn('flex flex-col gap-2')">
        <p v-if="category" class="font-thin">{{ category }}</p>
        <p class="text-xl">{{ title }}</p>
        <p v-if="description" class="font-light">{{ description }}</p>
        <p v-if="price">{{ price }} $</p>
        <UiButton v-if="buttonText">{{ buttonText }}</UiButton>
      </div>
    </UiCard>
  </div>
</template>

<script setup lang="ts">
import { cn } from "~/lib/utils";
import type { Product } from "./types";

defineProps<Product>();
</script>
