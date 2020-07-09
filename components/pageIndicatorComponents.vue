<template>
  <div class="container section-header">
    <div class="row">
      <div class="offset-lg-2 col-xl-8">
        <div class="card text-center page-indicator">
          <h3 class="text-uppercase">
            {{ firstTitle }}
            <span class="text-danger">{{ secondTitle }}</span>
          </h3>
          <div class="row">
            <div class="offset-lg-6 mx-auto col-lg-5 col-md-5 col-sm-6">
              <nav aria-label="breadcrumb">
                <ol class="breadcrumb" style="background-color: transparent;">
                  <li class="breadcrumb-item">
                    <nuxt-link :to="{'path':'/'}">Home</nuxt-link>
                  </li>
                  <li
                    class="breadcrumb-item active"
                    aria-current="page"
                  >{{ firstTitle }} {{ secondTitle }}</li>
                </ol>
              </nav>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  props: ["firstTitle", "secondTitle"]
};
</script>
<style scoped>
.page-indicator {
  border-top-right-radius: 15px;
  border-top-left-radius: 15px;
  margin-top: -70px;
  z-index: 9999;
  box-shadow: none !important;
  background-color: white;
  border-color: transparent;
  width: 100%;
  padding: 1rem;
}
.section-header h3 {
  font-size: 32px;
  color: #111;
  text-transform: uppercase;
  text-align: center;
  font-weight: 700;
  position: relative;
  padding-bottom: 15px;
}
.section-header h3::before {
  content: "";
  position: absolute;
  display: block;
  width: 120px;
  height: 1px;
  bottom: 1px;
  left: calc(50% - 60px);
}
.section-header h3::after {
  content: "";
  position: absolute;
  display: block;
  width: 60px;
  height: 3px;
  background: #e33349;
  bottom: 0;
  left: calc(50% - 20px);
}
</style>