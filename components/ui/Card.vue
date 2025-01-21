<template>
  <div
    :class="
      cn(
        'h-full w-full px-8 pb-6 flex flex-col gap-3 bg-white-400 rounded-3xl bg-clip-padding backdrop-filter backdrop-blur-md bg-opacity-20 border border-gray-500/30',
        props.class
      )
    "
  >
    <slot />
  </div>
</template>

<script lang="ts" setup>
import { cn } from "~/lib/utils";

const props = defineProps<{ class?: string }>();
</script>
