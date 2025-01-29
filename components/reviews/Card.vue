<template>
  <UiCard class="pt-6">
    <div class="flex items-center gap-8">
      <NuxtImg
        :src="image"
        alt="Person image"
        class="w-12 h-12 object-cover rounded-full"
      />
      <div>
        <p v-if="name" class="font-thin">{{ name }}</p>
      </div>
    </div>
    <p v-if="description" class="font-light">
      {{ description }}
    </p>
  </UiCard>
</template>

<script setup lang="ts">
import type { Review } from "./types";

defineProps<Review>();
</script>
