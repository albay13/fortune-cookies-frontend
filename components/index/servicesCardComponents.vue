<template>
  <div class="container-fluid">
    <div class="col-lg-12">
      <div class="card service-card">
        <section id="services">
          <div class="container mt-3">
            <div class="row">
              <div class="col-lg-6 col-md-6 col-xs-12 hover-icon">
                <center>
                  <div class="service-icon">
                    <img src="images/reveal-a-fortune.jpg" />
                    <!-- Icon made by https://icon54.com/ from www.flaticon.com -->
                  </div>
                  <h5 class="mt-2 text-bold text-uppercase">
                    Reveal a Fortune
                  </h5>
                  <h6>
                    Everyone loves cracking open a fortune cookie at the end of
                    a meal. Now you can open as many as you want!
                  </h6>
                </center>
              </div>
              <div class="col-lg-6 col-md-6 col-xs-12 hover-icon">
                <center>
                  <div class="service-icon">
                    <img
                      src="images/write-a-fortune.jpg"
                      width="50"
                      height="50"
                    />
                    <!-- Icon made by http://www.freepik.com from www.flaticon.com -->
                  </div>
                  <h5 class="mt-2 text-bold text-uppercase">
                    Write your own-made up Fortune
                  </h5>
                  <h6>
                    Write your own-made fortune after cracking a fortune cookie.
                  </h6>
                </center>
              </div>
            </div>
          </div>
        </section>
      </div>
    </div>
  </div>
</template>
<style scoped>
.service-icon img {
  width: 90px;
  height: 90px;
  line-height: 90px;
  border-radius: 50%;
}
.service-card {
  border-top-right-radius: 15px;
  border-top-left-radius: 15px;
  margin-top: -100px;
  z-index: 99;
  box-shadow: none;
  background-color: white;
  border-color: 1px solid black;
}
</style>
