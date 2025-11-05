<template>
  <div class="landing-page">
    <!-- Banner Component -->
    <AppBanner />
    <!-- About section -->
    <section class="about">
      <h2 class="about-title">About Us</h2>
      <p class="subtitle">
        TechBank is a blockchain product company creating decentralized tools
        like TechBank, Dbank, and Dwallet to simplify digital finance. We
        empower users with secure, transparent, and user-friendly solutions for
        managing assets in the Web3 world.
      </p>
      <div class="feature-cards-parent">
        <div class="feature-card-count">
          <h2>4</h2>
          <p>Products</p>
        </div>
        <div class="feature-card-count-center">
          <h2>2000+</h2>
          <p>Active Users</p>
        </div>
        <div class="feature-card-count">
          <h2>1 m+</h2>
          <p>Downloads</p>
        </div>
      </div>
    </section>
    <!-- Project section -->
    <section class="projects">
      <p class="innovative">Innovative</p>
      <h2 class="products-head">PRODUCTS</h2>
      <div class="projects___card">
        <div
          class="projects___card-inner"
          v-for="(project, index) in projects"
          :key="index"
        >
          <div class="project-image-container">
            <!-- Overlay top image -->
            <img
              :src="project.topImage"
              alt="Top Image"
              class="project-top-image"
            />
            <img
              :src="project.image"
              :alt="project.title + ' Image'"
              class="project-main-image"
            />
          </div>
          <div class="projects___card-content">
            <div class="projects___card-content-left">
              <h2>{{ project.title }}</h2>
              <p>{{ project.description }}</p>
            </div>
            <div class="projects___card-content-right">
              <button class="projects___card-button">
                View <img src="@/assets/images/arrow.png" alt="arrow img" />
              </button>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Technologies Section -->
    <section class="technologies">
      <h2 class="technologies-title">Technologies</h2>
      <div class="technologies-grid">
        <img
          v-for="(logo, index) in technologies"
          :key="index"
          :src="logo"
          alt="Technology Logo"
          class="technology-logo"
        />
      </div>
    </section>

    <!-- Connected Brands Slider Component -->
    <ConnectedBrandsSlider :brands="connectedBrands" />

    <!-- blogs Section -->
    <section class="blogs">
      <p class="innovative">Techbank</p>
      <h2 class="technologies-title">Blogs</h2>
      <div class="slider-section">
        <BlogSlider :blogs="blogs" />
      </div>
    </section>
  </div>
</template>

<script>
import AppBanner from "@/components/Banner/Banner.vue";
import project1 from "@/assets/images/project1.png";
import project2 from "@/assets/images/project2.png";
import p1 from "@/assets/images/p1.png";
import p2 from "@/assets/images/p2.png";
import Logo01 from "@/assets/images/clients/Logo04.png";
import Logo02 from "@/assets/images/clients/Logo02.png";
import Logo03 from "@/assets/images/clients/Logo03.png";
import Logo04 from "@/assets/images/clients/Logo05.png";
import Logo05 from "@/assets/images/clients/Logo01.png";
import Logo06 from "@/assets/images/clients/Logo02.png";
import Logo07 from "@/assets/images/clients/Logo03.png";
import Logo08 from "@/assets/images/clients/Logo05.png";
import Logo09 from "@/assets/images/clients/Logo01.png";
import Logo10 from "@/assets/images/clients/Logo04.png";
import Logo11 from "@/assets/images/clients/Logo03.png";
import Logo12 from "@/assets/images/clients/Logo05.png";
import blog1 from "@/assets/images/blog/blog1.jpg.png";
import blog2 from "@/assets/images/blog/blog2.png";
import blog3 from "@/assets/images/blog/blog3.png";
import BlogSlider from "@/components/BlogSlider/BlogSlider.vue";

import ConnectedBrandsSlider from "@/components/ConnectedBrandsSlider/ConnectedBrandsSlider.vue";

export default {
  name: "LandingPage",
  components: {
    AppBanner,
    ConnectedBrandsSlider,
    BlogSlider,
  },
  data() {
    return {
      projects: [
        {
          title: "DWALLET",
          description:
            "A secure, intuitive crypto wallet for managing your digital assets",
          image: project1,
          topImage: p1,
        },
        {
          title: "DBANK",
          description:
            "A secure staking platform for earning rewards on your digital assets",
          image: project2,
          topImage: p2,
        },
      ],
      technologies: [
        Logo01,
        Logo02,
        Logo03,
        Logo04,
        Logo05,
        Logo06,
        Logo07,
        Logo08,
        Logo09,
        Logo10,
        Logo11,
        Logo12,
      ],
      connectedBrands: [
        {
          title: "BLUE TIGERS",
          description: "Fueling the Future of Film, Sports, and Technology.",
          image: require("@/assets/images/brand1.png"),
        },
        {
          title: "KOCHI BLUE TIGERS",
          description:
            "A dynamic cricket team redefining the game with passion and power.",
          image: require("@/assets/images/brand1.png"),
        },
        {
          title: "BLUE TIGERS LONDON",
          description:
            "A creative production house bringing bold stories to life.",
          image: require("@/assets/images/brand1.png"),
        },
        {
          title: "BLUE TIGERS LONDON",
          description:
            "A creative production house bringing bold stories to life.",
          image: require("@/assets/images/brand1.png"),
        },
        {
          title: "BLUE TIGERS LONDON",
          description:
            "A creative production house bringing bold stories to life.",
          image: require("@/assets/images/brand1.png"),
        },
        {
          title: "BLUE TIGERS LONDON",
          description:
            "A creative production house bringing bold stories to life.",
          image: require("@/assets/images/brand1.png"),
        },
      ],
      blogs: [
        {
          title: "Smart AI Chatbot",
          description:
            "Enhance customer engagement with personalized, AI-driven interactions.",
          image: blog1,
        },
        {
          title: "Smart AI Chatbot",
          description:
            "Enhance customer engagement with personalized, AI-driven interactions.",
          image: blog2,
        },
        {
          title: "Smart AI Chatbot",
          description:
            "Enhance customer engagement with personalized, AI-driven interactions.",
          image: blog3,
        },
        {
          title: "Smart AI Chatbot",
          description:
            "Enhance customer engagement with personalized, AI-driven interactions.",
          image: blog1,
        },
        {
          title: "Smart AI Chatbot",
          description:
            "Enhance customer engagement with personalized, AI-driven interactions.",
          image: blog2,
        },
        {
          title: "Smart AI Chatbot",
          description:
            "Enhance customer engagement with personalized, AI-driven interactions.",
          image: blog3,
        },
      ],
    };
  },
};
</script>

<style scoped>
.landing-page {
  max-width: 1300px;
  margin: 0 auto;
  padding: 20px;
}

.hero {
  text-align: center;
  padding: 60px 20px;
  background-color: #f5f5f5;
  border-radius: 8px;
  margin-bottom: 40px;
}

.hero h1 {
  font-size: 3em;
  color: #2c3e50;
  margin-bottom: 20px;
}

.subtitle {
  font-size: 1.5em;
  color: #666;
}

.features {
  padding: 40px 0;
}

.features h2 {
  text-align: center;
  margin-bottom: 40px;
}

.features-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 30px;
  padding: 20px;
}

.feature-card {
  padding: 30px;
  background: white;
  border-radius: 8px;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
  transition: transform 0.3s ease;
}

.feature-card:hover {
  transform: translateY(-5px);
}

.feature-card h3 {
  color: #2c3e50;
  margin-bottom: 15px;
}

.feature-card p {
  color: #666;
  line-height: 1.6;
}
.about-title {
  text-align: center;
  font-family: "NYXERIN", Arial, sans-serif;
  color: #fff;
  padding-bottom: 20px;
  font-size: 27px;
}
.about {
  margin: 100px 0px;
}
.subtitle {
  text-align: center;
  padding: 0px 275px;
  color: #c0c0c0;
  font-size: 16px;
  padding-bottom: 40px;
}
.feature-cards-parent {
  text-align: center;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 50px;
}
.feature-card-count-center {
  border-left: 1px solid #c0c0c03d;
  border-right: 1px solid #c0c0c03d;
  padding: 0px 50px;
}
.feature-card-count h2 {
  font-size: 27px;
  font-family: "NYXERIN", Arial, sans-serif;
  color: #fff;
  margin-bottom: 10px;
}
.feature-card-count-center h2 {
  font-size: 27px;
  font-family: "NYXERIN", Arial, sans-serif;
  color: #fff;
  margin-bottom: 10px;
}
.feature-card-count p {
  font-size: 16px;
  color: #c0c0c0;
}
.feature-card-count-center p {
  font-size: 16px;
  color: #c0c0c0;
}
.innovative {
  text-align: center;
  color: #bb83ff;
  font-size: 16px;
  padding-bottom: 10px;
}
.products-head {
  text-align: center;
  font-family: "NYXERIN", Arial, sans-serif;
  color: #fff;
  font-size: 27px;
  margin-bottom: 40px;
}
.projects___card-inner {
  border: 1px solid #d9d9d9;
  display: flex;
  flex-direction: column;
  border-radius: 30px;
  /* align-items: center; */
  padding: 10px 10px 20px 10px;
}
.projects___card {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 40px;
  margin-top: 70px;
}
.projects___card-content {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.projects___card-content-left h2 {
  font-family: "NYXERIN", Arial, sans-serif;
  color: #fff;
  margin: 15px 0px;
}
.projects___card-content-left p {
  color: #c0c0c0;
  max-width: 350px;
}
.projects___card-button {
  background: linear-gradient(103.84deg, #330694 17.98%, #8500a6 69.45%);
  color: #fff;
  border: none;
  display: flex;
  align-items: center;
  gap: 15px;
  padding: 15px 40px;
  border-radius: 30px;
  font-weight: 600;
  cursor: pointer;
}
.project-image-container {
  position: relative;
}
.project-top-image {
  position: absolute;
  bottom: 20px;
  max-width: 40px;
  left: 3%;
}
.project-main-image {
  width: 100%;
}
.technologies {
  margin-top: 150px;
}
.technologies-title {
  color: #fff;
  font-family: "NYXERIN", Arial, sans-serif;
  text-align: center;
  padding-bottom: 20px;
}
.technologies-grid img {
  max-width: 150px;
  padding-bottom: 15px;
}
.technologies-grid {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr 1fr 1fr 1fr;
  gap: 25px;
  margin-top: 50px;
  align-items: center;
}
.connected-brands {
  margin-top: 150px;
}
.connected-brands-grid {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  gap: 30px;
  margin-top: 30px;
}
.connected-grid-card-wrapper {
  background: linear-gradient(
    151.62deg,
    #bb83ff 1.55%,
    #b1b1b1 28.63%,
    #313131 115.73%
  );
  border-radius: 20px;
  padding: 1px; /* border thickness */
}

.connected-grid-card {
  background: #0d0d0d;
  border-radius: 18px;
  color: #fff;

  padding: 30px 16px 0px 16px;
  transition: transform 0.3s ease;
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
.blogs {
  margin-top: 150px;
}
/* Swiper Navigation Buttons */
.swiper-button-prev,
.swiper-button-next {
  color: #bb83ff;
  transition: color 0.3s ease;
}

.swiper-button-prev:hover,
.swiper-button-next:hover {
  color: #fff;
}

/* Pagination Dots */
.swiper-pagination-bullet {
  background: #666;
  opacity: 1;
  transition: background 0.3s;
}

.swiper-pagination-bullet-active {
  background: #bb83ff;
}
.blog-image {
  max-width: 400px;
}
.swiper-backface-hidden .swiper-slide {
  background: #2b2b2b !important;
  border-radius: 30px !important;
}
.blog-content {
  padding: 30px 20px 50px 20px;
  color: #fff;
}
.blog-content h2 {
  color: #fff;
  padding-bottom: 10px;
}
.slider-section {
  margin-top: 50px;
}

/* responsive */
@media (min-width: 300px) and (max-width: 567px) {
  .projects___card {
    grid-template-columns: 1fr;
  }
  .technologies-grid {
    grid-template-columns: 1fr 1fr;
  }
  .subtitle {
    padding: 0px 0px;
  }
  .feature-cards-parent {
    gap: 20px;
    margin-top: 15px;
  }
  .feature-card-count-center {
    padding: 0px 20px;
  }
  .landing-page {
    padding: 0px;
    margin: 20px;
  }
  .about-title {
    padding-bottom: 30px;
  }
  .feature-card-count h2 {
    font-size: 20px;
  }
  .feature-card-count-center h2 {
    font-size: 20px;
  }
}
</style>
