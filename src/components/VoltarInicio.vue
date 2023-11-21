<template>
  <v-btn
    @click="scrollToTop"
    v-if="showButton"
    class="back-to-top"
    fab
    dark
    bottom
    right
  >
    <v-icon icon="fas fa-chevron-up"></v-icon>
  </v-btn>
</template>

<script>
export default {
  data() {
    return {
      showButton: false,
    };
  },
  methods: {
    scrollToTop() {
      window.scrollTo({
        top: 0,
        behavior: "smooth",
      });
    },
    handleScroll() {
      this.showButton = window.scrollY > 200;
    },
  },
  mounted() {
    window.addEventListener("scroll", this.handleScroll);
  },
  beforeDestroy() {
    window.removeEventListener("scroll", this.handleScroll);
  },
};
</script>

<style scoped>
.back-to-top {
  position: fixed;
  bottom: 30px;
  right: 30px;
  background-color: #2196f3;
  color: #fff; 
  border-radius: 10px; 
  width: 48px;
  height: 48px;
}
</style>
