<template>
  <div class="navbar-container">
    <nav class="navbar">
      <!-- Brand logo -->
      <div class="nav-brand">
        <router-link to="/">
          <img
            src="@/assets/images/logo.svg"
            alt="TechBank Logo"
            class="logo"
          />
        </router-link>
      </div>
      <!-- hambuger menu -->
      <div class="hamburger" @click="toggleMenu">
        <span :class="{ open: isMenuOpen }"></span>
        <span :class="{ open: isMenuOpen }"></span>
        <span :class="{ open: isMenuOpen }"></span>
      </div>

      <!-- 
      <div class="nav-links">
        <router-link to="/">Home</router-link>
        <router-link to="/products">Products</router-link>
        <router-link to="/teams">Teams</router-link>
        <router-link to="/career">Career</router-link>
        <router-link to="/blog">Blog</router-link>
      </div>
      <div>
        <button class="contact-button">
          <router-link to="/contact">Contact</router-link>
        </button>
      </div>  -->

      <div :class="['nav-links', { open: isMenuOpen }]">
        <router-link to="/" @click="closeMenu">Home</router-link>
        <router-link to="/products" @click="closeMenu">Products</router-link>
        <router-link to="/teams" @click="closeMenu">Teams</router-link>
        <router-link to="/career" @click="closeMenu">Career</router-link>
        <router-link to="/blog" @click="closeMenu">Blog</router-link>
        <button class="contact-button-mobile" @click="closeMenu">
          <router-link to="/contact">Contact</router-link>
        </button>
      </div>
      <div>
        <button class="contact-button">
          <router-link to="/contact">Contact</router-link>
        </button>
      </div>
    </nav>
  </div>
</template>

<script>
export default {
  name: "AppNavbar",
  data() {
    return {
      isMenuOpen: false,
    };
  },
  methods: {
    toggleMenu() {
      this.isMenuOpen = !this.isMenuOpen;
    },
    closeMenu() {
      this.isMenuOpen = false;
    },
  },
};
</script>

<style scoped>
.navbar {
  padding: 1rem 2rem;
  padding-left: 6%;
  padding-right: 6%;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.nav-brand {
  color: white;
  font-size: 1.5rem;
  font-weight: bold;
}

.nav-links {
  display: flex;
  gap: 20px;
}

.nav-links a {
  color: white;
  text-decoration: none;
  padding: 0.5rem 1rem;
  border-radius: 4px;
  transition: background-color 0.3s ease;
}

.nav-links a:hover {
  color: #e1c8ff;
}

.nav-links a.router-link-active {
  color: #e1c8ff;
}
.contact-button {
  background: transparent;
  color: #fff;
  border: 1px solid #fff;
  padding: 10px 40px;
  border-radius: 30px;
  cursor: pointer;
}
.contact-button-mobile {
  background: transparent;
  color: #fff;
  border: 1px solid #fff;
  padding: 10px 40px;
  border-radius: 30px;
  cursor: pointer;
  display: none;
}
.contact-button a {
  color: white;
  text-decoration: none;
}
.contact-button-mobile a {
  color: white;
  text-decoration: none;
}

/* ===== Hamburger Menu ===== */
.hamburger {
  display: none;
  flex-direction: column;
  justify-content: space-between;
  width: 26px;
  height: 18px;
  cursor: pointer;
  z-index: 1001;
}

.hamburger span {
  display: block;
  height: 3px;
  width: 100%;
  background: white;
  border-radius: 2px;
  transition: all 0.3s ease-in-out;
}

/* Hamburger open animation */
.hamburger span.open:nth-child(1) {
  transform: rotate(45deg) translateY(7px);
}
.hamburger span.open:nth-child(2) {
  opacity: 0;
}
.hamburger span.open:nth-child(3) {
  transform: rotate(-45deg) translateY(-7px);
}

/* ===== Mobile Menu ===== */
@media (max-width: 850px) {
  .hamburger {
    display: flex;
  }
  .contact-button-mobile {
    display: block;
  }
  .contact-button {
    display: none;
  }

  .nav-links {
    position: absolute;
    top: 10%;
    right: 0;
    background: linear-gradient(103.84deg, #330694 17.98%, #8500a6 69.45%);
    flex-direction: column;
    width: 100%;
    text-align: center;
    padding: 1.5rem 0;
    border-radius: 0 0 20px 20px;
    max-height: 0;
    overflow: hidden;
    opacity: 0;
    pointer-events: none;
    z-index: 9999;
  }

  .nav-links.open {
    max-height: 100%;
    opacity: 1;
    pointer-events: all;
    animation: slideDown 0.4s ease forwards;
  }

  @keyframes slideDown {
    from {
      transform: translateY(-10%);
      opacity: 0;
    }
    to {
      transform: translateY(0);
      opacity: 1;
    }
  }

  .nav-links a {
    display: block;
    padding: 0.8rem;
  }

  .contact-button {
    margin-top: 10px;
    width: 80%;
  }
}
</style>
