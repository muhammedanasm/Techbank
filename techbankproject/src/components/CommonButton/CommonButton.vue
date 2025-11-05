<template>
  <button
    :class="['common-btn', customClass]"
    :type="type"
    @click="$emit('click')"
  >
    <slot />
  </button>
</template>

<script>
export default {
  name: "CommonButton",
  props: {
    type: {
      type: String,
      default: "button",
    },
    customClass: {
      type: String,
      default: "",
    },
  },
};
</script>

<style scoped>
@font-face {
  font-family: "Ninetea";
  src: url("@/assets/fonts/Ninetea Font/Ninetea-Regular.otf") format("opentype");
  font-weight: normal;
  font-style: normal;
}
.common-btn {
  font-family: "Ninetea", Arial, sans-serif;
  background-color: #42b983;
  color: white;
  border: none;
  border-radius: 4px;
  padding: 12px 24px;
  font-size: 1em;
  cursor: pointer;
  transition: background-color 0.3s ease;
}
.common-btn:hover {
  background-color: #2c3e50;
}
</style>
