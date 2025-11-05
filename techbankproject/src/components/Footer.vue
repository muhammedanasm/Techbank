<template>
  <footer class="footer">
    <div class="footer-img">
      <img
        src="@/assets/images/footer.png"
        alt="footerimg"
        class="footer-img"
      />
    </div>
    <div class="footer-container">
      <div class="footer-head">
        <router-link to="/">
          <img
            src="@/assets/images/logo.svg"
            alt="TechBank Logo"
            class="logo"
          />
        </router-link>
        <p>hi@techbank.com</p>
      </div>
      <div class="footer-main">
        <div class="footer-nav">
          <h3>
            Engineering <br />
            the Future
          </h3>
          <button class="contact-us">Contact us</button>
        </div>
        <div class="footer-nav">
          <div class="footer-links">
            <p>Home</p>
            <p>Products</p>
            <p>Teams</p>
            <p>Career</p>
            <p>Blog</p>
          </div>
        </div>
        <div class="footer-nav">
          <p>Offices</p>
          <div class="address">
            <p>Infopark</p>
            <p>Kochi - Kerala</p>
          </div>
        </div>
      </div>
      <div class="socila-media-copyrihgts">
        <div class="social-media-icons">
          <AnOutlinedLinkedin />
          <AkInstagramFill />
          <BsTwitterX />
          <AnOutlinedYoutube />
        </div>
        <div class="copy-right">© 2025 Techbank</div>
        <div class="terms-policy">
          <p>Privacy Policy</p>
          <p>Terms and Conditions</p>
        </div>
      </div>
    </div>
  </footer>
</template>

<script>
import {
  AnOutlinedLinkedin,
  AkInstagramFill,
  BsTwitterX,
  AnOutlinedYoutube,
} from "@kalimahapps/vue-icons";
export default {
  name: "AppFooter",
  components: {
    AnOutlinedLinkedin,
    AkInstagramFill,
    BsTwitterX,
    AnOutlinedYoutube,
  },
};
</script>

<style scoped>
.footer {
  color: white;
  position: relative;
  overflow: hidden;
  margin-top: 100px;
}
.footer-img {
  position: absolute;
  bottom: -2%;
  left: 0%;
  height: -webkit-fill-available;
  width: 100%;
}
.footer-container {
  position: relative;
  padding-left: 6%;
  padding-right: 6%;
}
.footer-head {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding-bottom: 50px;
}
.footer-main {
  display: grid;
  grid-template-columns: 3fr 1fr 1.3fr;
  padding-bottom: 40px;
}
.socila-media-copyrihgts {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding-bottom: 150px;
}
.social-media-icons {
  display: flex;
  align-items: center;
  gap: 15px;
  cursor: pointer;
}
.terms-policy {
  display: flex;
  align-items: center;
  gap: 15px;
}
.footer-links p:nth-child(1) {
  border-bottom: 1px solid #ffffff99;
  display: inline-block;
}
.footer-links p {
  margin-bottom: 15px;
  cursor: pointer;
}
.footer-nav h3 {
  font-family: "NYXERIN", Arial, sans-serif;
  line-height: 30px;
  letter-spacing: 2px;
  font-size: 24px;
  padding-bottom: 30px;
}
.contact-us {
  background: transparent;
  color: #fff;
  border: 1px solid #fff;
  padding: 10px 30px;
  border-radius: 30px;
  cursor: pointer;
}
.footer-links p:hover {
  color: #e1c8ff;
}

.address {
  padding-top: 30px;
}
/* responsive */
@media (min-width: 300px) and (max-width: 567px) {
  .footer-main {
    grid-template-columns: 1fr;
  }
  .socila-media-copyrihgts {
    flex-direction: column;
    gap: 15px;
  }
  .social-media-icons {
    gap: 30px;
    cursor: pointer;
    font-size: 20px;
    border-bottom: 1px solid #fbfdff26;
    padding-bottom: 15px;
    width: 100%;
    align-items: center;
    justify-content: center;
  }
  .copy-right {
    border-bottom: 1px solid #fbfdff26;
    padding-bottom: 15px;
    width: 100%;
    text-align: center;
  }
  .footer-links {
    margin-top: 30px;
  }
}
</style>
