<template>
  <swiper
    :modules="[
      require('swiper/modules').Navigation,
      require('swiper/modules').Pagination,
      require('swiper/modules').Autoplay,
      require('swiper/modules').Mousewheel,
    ]"
    :slides-per-view="3"
    :space-between="30"
    :loop="true"
    :autoplay="{ delay: 2500, disableOnInteraction: false }"
    :breakpoints="{
      320: { slidesPerView: 1, mousewheel: true },
      768: { slidesPerView: 2, mousewheel: true },
      1024: { slidesPerView: 3, mousewheel: true },
    }"
    navigation
    :pagination="{ clickable: true }"
    :mousewheel="{ forceToAxis: true, sensitivity: 1 }"
    class="blogs-swiper"
  >
    <swiper-slide v-for="(blog, index) in blogs" :key="index" class="blog-card">
      <img :src="blog.image" :alt="blog.title" class="blog-image" />
      <div class="blog-content">
        <h2>{{ blog.title }}</h2>
        <p>{{ blog.description }}</p>
      </div>
    </swiper-slide>
  </swiper>
</template>

<script>
import { Swiper, SwiperSlide } from "swiper/vue";
import "swiper/css";
import "swiper/css/navigation";
import "swiper/css/pagination";
import "swiper/css/mousewheel";

export default {
  name: "BlogSlider",
  components: {
    swiper: Swiper,
    "swiper-slide": SwiperSlide,
  },
  props: {
    blogs: {
      type: Array,
      required: true,
    },
  },
};
</script>

<style scoped></style>
