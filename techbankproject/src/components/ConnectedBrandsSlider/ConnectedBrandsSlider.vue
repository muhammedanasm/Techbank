<template>
  <section class="connected-brands-slider">
    <p class="innovative">From One Root, Many Branches</p>
    <h2 class="technologies-title">Connected Brands</h2>

    <swiper
      :modules="[
        require('swiper/modules').Navigation,
        require('swiper/modules').Pagination,
        require('swiper/modules').Autoplay,
      ]"
      :slides-per-view="3"
      :space-between="30"
      :loop="true"
      :autoplay="{
        delay: 2500,
        disableOnInteraction: false,
        pauseOnMouseEnter: true,
      }"
      :speed="700"
      :breakpoints="{
        320: { slidesPerView: 1 },
        768: { slidesPerView: 2 },
        1200: { slidesPerView: 3 },
      }"
      class="connected-brands-swiper"
    >
      <swiper-slide
        v-for="(brand, index) in brands"
        :key="index"
        class="connected-grid-card-wrapper"
      >
        <div class="connected-grid-card">
          <h3>{{ brand.title }}</h3>
          <p class="brand-desc">{{ brand.description }}</p>

          <div class="social-media-icons">
            <AnOutlinedLinkedin />
            <AkInstagramFill />
            <BsTwitterX />
            <AnOutlinedYoutube />
          </div>

          <div class="image-wrapper">
            <img :src="brand.image" alt="Connected Brand Image" />
          </div>
        </div>
      </swiper-slide>
    </swiper>
  </section>
</template>

<script>
import { Swiper, SwiperSlide } from "swiper/vue";
import "swiper/css";
import "swiper/css/navigation";
import "swiper/css/pagination";
import {
  AnOutlinedLinkedin,
  AkInstagramFill,
  BsTwitterX,
  AnOutlinedYoutube,
} from "@kalimahapps/vue-icons";

export default {
  name: "ConnectedBrandsSlider",
  components: {
    swiper: Swiper,
    "swiper-slide": SwiperSlide,
    AnOutlinedLinkedin,
    AkInstagramFill,
    BsTwitterX,
    AnOutlinedYoutube,
  },
  props: {
    brands: {
      type: Array,
      required: true,
    },
  },
};
</script>

<style scoped>
.connected-brands-slider {
  margin-top: 150px;
}
.connected-brands-swiper {
  margin-top: 30px;
  width: 100%;
  --carousel-gap: 0px;
}
.connected-grid-card-wrapper {
  background: linear-gradient(
    151.62deg,
    #bb83ff 1.55%,
    #b1b1b1 28.63%,
    #313131 115.73%
  );
  border-radius: 20px;
  padding: 1px;
  height: 100%;
  display: flex;
  align-items: stretch;
  margin-right: var(--carousel-gap);
}
.connected-grid-card {
  background: #0d0d0d;
  border-radius: 18px;
  color: #fff;
  padding: 30px 16px 0px 16px;
  transition: transform 0.3s ease;
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}
.connected-grid-card-wrapper {
  position: relative;
  border-radius: 20px;
  height: 100%;
  display: flex;
  align-items: stretch;
  margin-right: var(--carousel-gap);
  overflow: hidden;
  background: linear-gradient(
    151.62deg,
    #bb83ff 1.55%,
    #b1b1b1 28.63%,
    #313131 115.73%
  );
}
.connected-grid-card {
  background: #0d0d0d;
  border-radius: inherit;
  color: #fff;
  padding: 30px 16px 0px 16px;
  transition: transform 0.3s ease;
  height: 100%;
  flex: 1;
}
.connected-grid-card h3 {
  font-size: 24px;
  font-weight: 400;
  padding-bottom: 5px;
}
.connected-grid-card p {
  color: #a9a9a9;
  padding-bottom: 15px;
}
.social-media-icons {
  font-size: 24px;
  display: flex;
  align-items: center;
  gap: 20px;
  cursor: pointer;
}
.image-wrapper {
  margin-top: 20px;
  text-align: center;
}
.image-wrapper img {
  width: 100%;

  border-radius: 12px;
  object-fit: cover;
}
.brand-desc {
  max-width: 300px;
}
.innovative {
  text-align: center;
  color: #bb83ff;
  font-size: 16px;
  padding-bottom: 10px;
}
.technologies-title {
  color: #fff;
  font-family: "NYXERIN", Arial, sans-serif;
  text-align: center;
  padding-bottom: 20px;
}
</style>
