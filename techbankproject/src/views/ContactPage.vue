<template>
  <div class="contact-page">
    <div class="contact-container">
      <!-- Left Side Image + Text -->
      <div class="contact-left">
        <img
          src="@/assets/images/contactpage.png"
          alt="TechBank Contact"
          class="contact-image"
        />
      </div>

      <!-- Right Side Form -->
      <div class="contact-right">
        <p class="contact-title">BUILD THE FUTURE WITH US</p>
        <h1 class="contact-heading">CONTACT US</h1>

        <form @submit.prevent="submitForm" class="contact-form">
          <div class="form-group">
            <label for="name">Name *</label>
            <input
              type="text"
              id="name"
              v-model="form.name"
              required
              placeholder="Enter Your Name"
            />
          </div>

          <div class="form-group">
            <label for="email">Email *</label>
            <input
              type="email"
              id="email"
              v-model="form.email"
              required
              placeholder="Enter Email"
            />
          </div>

          <div class="form-group phone-group">
            <label for="phone">Phone Number *</label>
            <div class="phone-input">
              <div class="country-select">
                <select v-model="selectedCountry" class="country-select">
                  <option value="+91">🇮🇳 +91</option>
                  <option value="+1">🇺🇸 +1</option>
                  <option value="+44">🇬🇧 +44</option>
                </select>
              </div>
              <input
                type="tel"
                id="phone"
                v-model="form.phone"
                required
                placeholder="Enter Your Phone Number"
              />
            </div>
          </div>

          <div class="form-group">
            <label for="message">Message</label>
            <textarea
              id="message"
              v-model="form.message"
              rows="5"
              placeholder="Write your message"
            ></textarea>
          </div>

          <button type="submit" class="submit-button">
            Send Message <AkArrowUpRight class="arrow-icon" />
          </button>
        </form>
      </div>
    </div>
  </div>
</template>

<script>
import { AkArrowUpRight } from "@kalimahapps/vue-icons";
export default {
  name: "ContactPage",
  components: {
    AkArrowUpRight, // 👈 register the icon here
  },
  data() {
    return {
      selectedCountry: "+91",
      form: {
        name: "",
        email: "",
        phone: "",
        message: "",
      },
    };
  },
  methods: {
    submitForm() {
      console.log("Form submitted:", this.form);
      alert("Thank you for your message! We’ll get back to you soon.");
      this.form = { name: "", email: "", phone: "", message: "" };
    },
  },
};
</script>

<style scoped>
.contact-page {
  background-color: #000;
  color: #fff;
  min-height: 100vh;
  padding: 60px 8%;
  display: flex;
  justify-content: center;
  align-items: center;
}

.contact-container {
  display: grid;
  grid-template-columns: 1fr 1fr;
  align-items: center;
  gap: 60px;
  width: 100%;
  max-width: 1400px;
}

/* LEFT SIDE */
.contact-left {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
}

.contact-image {
  width: 80%;
  border-radius: 20px;
  box-shadow: 0 0 30px rgba(128, 0, 255, 0.3);
  margin-bottom: 20px;
}

.contact-tagline {
  font-family: "Orbitron", sans-serif;
  font-weight: 500;
  font-size: 1rem;
  letter-spacing: 1px;
  line-height: 1.5;
  max-width: 80%;
}

/* RIGHT SIDE FORM */
.contact-right {
  background: #0b0b0b;
  padding: 40px;
  border-radius: 20px;
  box-shadow: 0 0 25px rgba(128, 0, 255, 0.25);
}

.contact-title {
  color: #9b6fff;
  margin-bottom: 5px;
  font-size: 14px;
}

.contact-heading {
  margin-bottom: 30px;
  letter-spacing: 1px;
  font-family: "NYXERIN", Arial, sans-serif;
}

.form-group {
  margin-bottom: 20px;
}

.form-group label {
  font-size: 0.9rem;
  color: #ccc;
  display: block;
  margin-bottom: 8px;
}

.form-group input,
.form-group textarea {
  width: 100%;
  background: #1a1a1a;
  border: 1px solid #474747;
  border-radius: 8px;
  padding: 12px 16px;
  color: #fff;
  font-size: 0.95rem;
  outline: none;
  transition: border 0.3s ease;
}
.form-group input::placeholder,
.form-group textarea::placeholder {
  color: #4e4e4e;
}

.form-group input:focus,
.form-group textarea:focus {
  border-color: #8b5cf6;
}

.submit-button {
  background: linear-gradient(103.84deg, #330694 17.98%, #8500a6 69.45%);
  color: #fff;
  display: flex;
  align-items: center;
  gap: 20px;
  border: none;
  padding: 5px 5px 5px 20px;
  border-radius: 30px;
  cursor: pointer;
  transition: all 0.3s ease;
}
.submit-button svg {
  background: #fff;
  color: #8501a6;
  font-size: 38px;
  border-radius: 30px;
  padding: 10px;
}

.submit-button:hover {
  background: linear-gradient(103.84deg, #8500a6 17.98%, #330694 69.45%);
  box-shadow: 0 0 15px rgba(139, 92, 246, 0.6);
}

.arrow {
  font-size: 1.2rem;
}
.phone-input {
  display: flex;
  align-items: center;
  gap: 8px;
  background: #1a1a1a;
  border: 1px solid #474747;
  border-radius: 8px;
  padding: 8px 12px;
  transition: border 0.3s ease;
}

.phone-input:focus-within {
  border-color: #8b5cf6;
}

.country-select {
  display: flex;
  align-items: center;
  gap: 6px;
  background: #1a1a1a;
  border-right: 1px solid #474747;
  padding-right: 8px;
}

.country-select img {
  width: 20px;
  height: 15px;
  border-radius: 3px;
}

.country-select select {
  background: transparent;
  border: none;
  color: #fff;
  font-size: 0.95rem;
  outline: none;
  cursor: pointer;
}

.phone-input input {
  flex: 1;
  background: transparent;
  border: none;
  color: #fff;
  font-size: 0.95rem;
  outline: none;
}

.phone-input input::placeholder {
  color: #4e4e4e;
}

/* Responsive */
@media (max-width: 992px) {
  .contact-container {
    grid-template-columns: 1fr;
    gap: 0px;
  }
  .contact-right {
    margin-top: 40px;
    padding-left: 0px;
    padding-right: 0px;
  }
  .contact-heading {
    font-size: 27px;
  }
  .contact-image {
    width: 100%;
  }
}
</style>
