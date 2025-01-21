<template>
  <div class="pt-16">
    <UiCard
      :class="
        cn({ 'md:flex-row items-center justify-center md:gap-20': horizontal })
      "
    >
      <NuxtImg
        :src="imageSrc"
        alt="Product image"
        :class="
          cn('-mt-16 h-52 w-fit mx-auto md:h-72', {
            'mx-0 md:h-96': horizontal,
          })
        "
      />
      <div :class="cn('flex flex-col gap-2')">
        <p v-if="category" class="font-thin">{{ category }}</p>
        <p
          :class="
            cn('font-light text-xl md:text-2xl', { 'md:text-3xl': horizontal })
          "
        >
          {{ title }}
        </p>
        <p v-if="description" class="font-light md:text-xl">
          {{ description }}
        </p>
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
