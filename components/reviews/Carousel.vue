<template>
  <div class="w-full container">
    <SectionTitle>Reviews</SectionTitle>
    <Splide
      :options="{
        rewind: true,
        arrows: false,
        gap: 16,
        perPage: 3,
        breakpoints: {
          576: {
            perPage: 1,
          },
          768: {
            perPage: 2,
          },
        },
      }"
      aria-label="My Favorite Images"
    >
      <SplideSlide v-for="(review, index) in reviews" :key="index">
        <ReviewsCard
          :description="review.description"
          :image="review.image"
          :name="review.name"
          :rating="review.rating"
        />
      </SplideSlide>
    </Splide>
  </div>
</template>

<script setup lang="ts">
import "@splidejs/vue-splide/css";
import { Splide, SplideSlide } from "@splidejs/vue-splide";

const reviews = [
  {
    name: "John Doe",
    description:
      "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.",
    image: "/images/avatar.webp",
    rating: 4,
  },
  {
    name: "John Doe",
    description:
      "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.",
    image: "/images/avatar.webp",
    rating: 4,
  },
  {
    name: "John Doe",
    description:
      "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.",
    image: "/images/avatar.webp",
    rating: 4,
  },
  {
    name: "John Doe",
    description:
      "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.",
    image: "/images/avatar.webp",
    rating: 4,
  },
];
</script>
