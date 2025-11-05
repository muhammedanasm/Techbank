<template>
  <section class="banner">
    <div class="banner-img">
      <img
        src="@/assets/images/banner.png"
        alt="Banner Image"
        class="banner-image"
      />
      <!--
<img
  src="@/assets/images/bannermob.png"
  alt="Banner Image"
  class="banner-image-mobile"
/>
-->
      <div class="banner_title_top">
        <img src="@/assets/images/circle.png" alt="Banner Top Image" />
        <p>
          At TechBank, we’re pioneering the technologies of tomorrow. From
          blockchain to AI, we’re building the digital landscape of the future,
          today.
        </p>
      </div>
      <div class="banner-title">
        Engineering <br />
        the Future
      </div>
      <div class="banner-title-bottom">
        <p>
          Empowering Businesses, Enabling Growth TechBank’s Products for Success
        </p>
        <button class="view-products">
          View Products <AkArrowUpRight class="arrow-icon" />
        </button>
      </div>
      <div class="banner-small-img">
        <img
          src="@/assets/images/bannersmall.png"
          alt="Small Banner Image"
          class="small-banner-image"
        />
      </div>
      <div class="banner-gif">
        <img src="@/assets/gif/comp.gif" alt="Animated GIF" class="gif-image" />
      </div>
    </div>
    <div class="scroll-prompt">+ SCROLL TO EXPLORE +</div>
  </section>
</template>

<script>
import { AkArrowUpRight } from "@kalimahapps/vue-icons";
export default {
  name: "AppBanner",
  components: {
    AkArrowUpRight, // 👈 register the icon here
  },
};
</script>

<style scoped>
@font-face {
  font-family: "NYXERIN";
  src: url("@/assets/fonts/nyxerin/NYXERIN.otf") format("opentype");
  font-weight: normal;
  font-style: normal;
}
@font-face {
  font-family: "Ninetea";
  src: url("@/assets/fonts/Ninetea Font/Ninetea-Regular.otf") format("opentype");
  font-weight: normal;
  font-style: normal;
}

.banner-title {
  font-family: "NYXERIN", Arial, sans-serif;
  font-size: 3em;
  margin-bottom: 20px;
  margin: 0;
  position: absolute;
  top: 65%;
  left: 50%;
  transform: translate(-50%, -50%);
  z-index: 1;
  font-size: 84px;
  line-height: 92px;
}
.banner-subtitle {
  font-family: "Ninetea", Arial, sans-serif;
  font-size: 1.5em;
}
.banner-img {
  position: relative;
}
.banner-gif img {
  height: 600px;
  margin: 0;
  position: absolute;
  top: 15%;
  left: 35%;
  transform: translate(-50%, -50%);
  transform: rotate(39deg);
}
.banner-small-img img {
  margin: 0;
  position: absolute;
  top: 30%;
  left: 50%;
  transform: translate(-50%, -50%);
}
.banner_title_top {
  display: flex;
}
.banner_title_top p {
  max-width: 390px;
}
.banner_title_top {
  position: absolute;
  top: 3%;
  right: 10%;
  color: #bababa;
}
.banner-title-bottom {
  display: flex;
  margin: 0;
  position: absolute;
  bottom: 3%;
  left: 50%;
  transform: translate(-50%, -50%);
  gap: 100px;
}
.banner-title-bottom p {
  max-width: 335px;
  color: #000;
}
.view-products {
  background: linear-gradient(103.84deg, #330694 17.98%, #8500a6 69.45%);
  color: #fff;
  display: flex;
  align-items: center;
  gap: 20px;
  border: none;
  padding: 0px 6px 0px 20px;
  border-radius: 30px;
  cursor: pointer;
}
.view-products svg {
  background: #fff;
  color: #8501a6;
  font-size: 38px;
  border-radius: 30px;
  padding: 10px;
}
.scroll-prompt {
  text-align: center;
  color: #fff;
  font-size: 14px;
  padding-top: 8px;
}

/* responsive */
@media (min-width: 300px) and (max-width: 567px) {
  .banner-title {
    position: absolute;
    top: 65%;
    left: 15%;
    transform: translate(-50%, -50%);
    z-index: 1;
    font-size: 35px;
    line-height: 57px;
  }
  .banner-image {
    width: 370px;
    height: 100vh;
  }
  .banner_title_top {
    display: none;
  }
  .banner-title-bottom {
    gap: 15px;
    flex-direction: column;
    bottom: 3%;
    left: 15%;
  }
  .banner-small-img img {
    left: 15%;
  }
  .banner-gif img {
    height: 500px;
    margin: 0;
    position: absolute;
    top: 15%;
    left: 2%;
  }
}
</style>
