<template>
  <div>
    <Navbar />
    <Nuxt />
  </div>
</template>
<script>
import Navbar from "@/components/navbarComponents";

export default {
  components: {
    Navbar
  }
};
</script>
<style>
* {
  margin: 0;
  padding: 0;
}
html,
body {
  height: 100%;
  font-family: "Dosis", sans-serif !important;
}
body {
  background-color: #e0e0e0;
}
</style>
