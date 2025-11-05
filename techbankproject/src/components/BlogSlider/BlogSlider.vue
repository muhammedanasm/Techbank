<template>
  <swiper
    :modules="[
      require('swiper/modules').Navigation,
      require('swiper/modules').Pagination,
      require('swiper/modules').Autoplay,
    ]"
    :slides-per-view="3"
    :space-between="30"
    :loop="true"
    :autoplay="{ delay: 2500, disableOnInteraction: false }"
    :breakpoints="{
      320: { slidesPerView: 1 },
      768: { slidesPerView: 2 },
      1200: { slidesPerView: 3 },
    }"
    navigation
    :pagination="{ clickable: true }"
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

<style scoped>
/* Responsive Swiper container */
.blogs-swiper {
  width: 100%;
  max-width: 100vw;
  box-sizing: border-box;
}

.blog-card {
  width: 100%;
  background: #2b2b2b;
  color: #fff;
  border-radius: 16px;

  text-align: center;
  display: flex;
  flex-direction: column;
  gap: 12px;
  box-sizing: border-box;
}

.blog-image {
  width: 100%;
  border-radius: 12px;
  object-fit: cover;
  height: 180px;
}

.blog-content {
  padding: 30px 20px 50px 20px;
  color: #fff;
  text-align: left;
}

.blog-content h2 {
  color: #fff;
  padding-bottom: 10px;
}
.swiper-pagination-bullet swiper-pagination-bullet-active {
  background: #fff !important;
}

@media (max-width: 767px) {
  .blogs-swiper {
    max-width: 100vw;
    padding: 0 4px;
  }
  .blog-card {
    min-width: 0;
    width: 100%;
    padding: 12px 6px;
  }
  .blog-image {
    height: 140px;
  }
  .blog-content {
    padding: 18px 8px 30px 8px;
  }
}
</style>
