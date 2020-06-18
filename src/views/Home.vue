<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png" />
    <CanvasTrianle msg="Welcome to Your Vue.js App" />
  </div>
</template>

<script>
// @ is an alias to /src
import CanvasTrianle from "@/components/CanvasTrianle.vue";

export default {
  name: "Home",
  components: {
    CanvasTrianle
  }
};
</script>

<style lang="scss" scoped>
.home {
  img {
    height: 50px;
  }
}
</style>