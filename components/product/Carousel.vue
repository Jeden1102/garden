<template>
  <div class="w-full md:w-[400px] mx-auto">
    <Splide
      :options="{ rewind: true, arrows: false, gap: 16 }"
      aria-label="My Favorite Images"
    >
      <SplideSlide v-for="(product, index) in products" :key="index">
        <ProductCard
          :title="product.title"
          :description="product.description"
          :category="product.category"
          :price="product.price"
          :buttonText="product.buttonText"
          :imageSrc="product.imageSrc"
        />
      </SplideSlide>
    </Splide>
  </div>
</template>

<script setup lang="ts">
import "@splidejs/vue-splide/css";
import { Splide, SplideSlide } from "@splidejs/vue-splide";
import type { Product } from "./types";

const props = defineProps<{
  products: Product[];
}>();
</script>

<style lang="scss">
ul.splide {
  &:not(.is-overflow) {
    .splide__pagination {
      @apply flex;
    }
  }
  &__pagination {
    @apply static flex pt-2;

    button {
      @apply h-[10px] w-[10px] rounded-full bg-white/90 transition-all;

      &.is-active {
        @apply w-[25px] transform-none bg-white;
      }
    }
  }
}
</style>
