<template>
  <div>
    <!-- IMAGE SLIDER -->
    <Slider />
    <!-- DISPLAY FUNCTIONALITY E.g Reveal a Fortune, Write own-made up fortune -->
    <ServicesCard />
    <Modal
      v-if="addFortune"
      @addFortune="addFortuneMessage"
      @cancel="cancel()"
      @close="close()"
    >
      <!-- POP-UP MODAL FOR ADDING FORTUNES -->
    </Modal>
    <br />
    <div class="container text-center my-5">
      <div class="row ">
        <div class="col-lg-12">
          <h1>ASK THE FORTUNE COOKIE</h1>
        </div>
      </div>
      <div class="row ">
        <div class="col-lg-12">
          <img
            class="img-fluid"
            v-if="!openCookie"
            src="/images/close_cookie.png"
            alt=""
          />
          <img class="img-fluid" v-else src="/images/open_cookie.png" alt="" />
          <center>
            <p v-if="openCookie" class="cookie-message">
              {{ cookieMessage }}
            </p>
          </center>
        </div>
      </div>
      <div class="row">
        <div class="col-lg-12">
          <button
            :disabled="btnDisabled || fortunes.length == 0"
            @click="crackCookie"
            class="btn btn-danger"
          >
            {{ btnText }}
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Slider from "@/components/index/sliderComponents";
import ServicesCard from "@/components/index/servicesCardComponents";
import Modal from "@/components/modalComponents";
export default {
  components: {
    Slider,
    ServicesCard,
    Modal
  },
  data() {
    return {
      openCookie: false,
      src: "close_cookie.png",
      btnText: "CRAK OPEN YOUR COOKIE",
      cookieMessage: "",
      addFortune: false,
      btnDisabled: false,
      cookieId: ""
    };
  },
  async asyncData({ $axios }) {
    let fortunes = await $axios.$get("/fortunes");
    return {
      fortunes: fortunes.data.length == 0 ? [] : fortunes.data
    };
  },
  watch: {
    openCookie(val) {
      if (val) {
        this.btnText = "CRAK OPEN ANOTHER COOKIE";
        this.src = "open_cookie.png";
      } else {
        this.btnText = "CRAK OPEN YOUR COOKIE";
        this.src = "open_cookie.png";
      }
    }
  },
  methods: {
    crackCookie() {
      if (this.openCookie) {
        this.addFortune = true;
      } else {
        this.openCookie = true;
        //RANDOMLY ACCESS ARRAY
        var data = this.fortunes[
          Math.floor(Math.random() * this.fortunes.length)
        ];
        this.cookieMessage = data.message;
        this.cookieId = data.id;
      }
    },
    addFortuneMessage(message) {
      this.$axios
        .patch(`/fortunes/${this.cookieId}`, { message: message })
        .then(res => {
          this.openCookie = false;
          this.addFortune = false;
          alert("You have successfully added a fortune.");
        });
    },
    cancel() {
      this.openCookie = false;
      this.addFortune = false;
    },
    close() {
      this.openCookie = false;
      this.addFortune = false;
    }
  },
  head: {
    title: "Welcome to Fortune Cookies"
  }
};
</script>

<style scoped>
.title {
  font-family: "Quicksand", "Source Sans Pro", -apple-system, BlinkMacSystemFont,
    "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
.cookie-message {
  position: relative;
  bottom: 190px;
  left: 12vh;
  max-width: 270px;
}
@media (max-width: 505px) {
  .cookie-message {
    position: relative;
    bottom: 190px;
    left: 13vh;
  }
}

@media (max-width: 482px) {
  .cookie-message {
    position: relative;
    bottom: 185px;
    left: 13vh;
  }
}
@media (max-width: 458px) {
  .cookie-message {
    position: relative;
    bottom: 175px;
    left: 13vh;
  }
}
@media (max-width: 420px) {
  .cookie-message {
    position: relative;
    bottom: 165px;
    left: 13vh;
  }
}
@media (max-width: 399px) {
  .cookie-message {
    position: relative;
    bottom: 155px;
    left: 13vh;
  }
}
@media (max-width: 374px) {
  .cookie-message {
    position: relative;
    bottom: 140px;
    left: 16vh;
    font-size: 15px;
    max-width: 180px;
  }
}
</style>
