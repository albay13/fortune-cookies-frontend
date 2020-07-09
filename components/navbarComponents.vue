<template>
  <div>
    <nav class="navbar navbar-expand-lg navbar-light fixed-top">
      <nuxt-link
        class="float-left navbar-brand text-uppercase ml-5"
        :to="{ path: '/' }"
      >
        <b>
          Fortune
          <span class="text-danger">Cookies</span>
        </b>
      </nuxt-link>
      <button
        class="navbar-toggler ml-auto"
        type="button"
        data-toggle="collapse"
        data-target="#navbarTogglerDemo02"
        aria-controls="navbarTogglerDemo02"
        aria-expanded="false"
        aria-label="Toggle navigation"
      >
        <span class="navbar-toggler-icon"></span>
      </button>

      <div class="collapse navbar-collapse" id="navbarTogglerDemo02">
        <ul class="navbar-nav ml-auto mr-5 mt-2 mt-lg-0">
          <li
            class="nav-item"
            :class="currentPath == '/' ? 'active' : 'non-active'"
          >
            <nuxt-link class="nav-link" :to="{ path: '/' }">
              Home
              <span class="sr-only">(current)</span>
            </nuxt-link>
          </li>
        </ul>
      </div>
    </nav>
  </div>
</template>
<script>
export default {
  data() {
    return {
      currentPath: ""
    };
  },
  watch: {
    $route: {
      handler(val) {
        this.currentPath = val.path;
      },
      immediate: true
    }
  }
};
</script>
<style scoped>
/*Navbar*/
.navbar-brand {
  font-size: 1.5rem;
  font-family: "Dosis", sans-serif;
}
.nav-link {
  font-size: 1rem;
  font-family: "Dosis", sans-serif;
}
.navbar {
  background-color: white;
  border: none;
  color: white;
  z-index: 999999;
  transition: background-color 1s ease;
}

.navbar.solid {
  background-color: #234360;
  transition: background-color 0.3s ease 0.1s;
  box-shadow: 0 0 4px grey;
}
ul.navbar-nav .nav-item.non-active:after {
  content: "";
  display: block;
  height: 2px;
  width: 0;
  transition: width 0.5s ease, background-color 0.5s ease;
}
.navbar-nav .nav-item.non-active:hover:after {
  width: 100%;
  background: #eb3719;
}

.navbar-nav .nav-item.active {
  border-bottom: 2px solid #eb3719;
}
.navbar-toggler {
  border-color: transparent !important;
}
/*Navbar Media Query*/
@media (max-width: 302px) and (min-width: 292px) {
  .navbar-brand {
    font-size: 1.4rem;
  }
}
@media (max-width: 291px) and (min-width: 282px) {
  .navbar-brand {
    font-size: 1.3rem;
  }
}
@media (max-width: 281px) and (min-width: 272px) {
  .navbar-brand {
    font-size: 1.2rem;
  }
  .navbar-toggler {
    font-size: 16px;
  }
}
@media (max-width: 271px) and (min-width: 262px) {
  .navbar-brand {
    font-size: 1.1rem;
  }
  .navbar-toggler {
    font-size: 15px;
  }
}
@media (max-width: 261px) and (min-width: 253px) {
  .navbar-brand {
    font-size: 1rem;
  }
  .navbar-toggler {
    font-size: 12px;
  }
}
@media (max-width: 252px) and (min-width: 210px) {
  .navbar-brand {
    font-size: 0.675rem;
  }
  .navbar-toggler {
    font-size: 10px;
  }
}
</style>
