<template>
  <div>
    <div id="demo" class="carousel slide carousel-fade" data-ride="carousel">
      <!-- The slideshow -->
      <div class="carousel-inner">
        <div class="carousel-item active">
          <img
            src="images/bowl-of-cookies-slider-1.jpg"
            class="d-block w-100 mh-100"
            alt="Los Angeles"
            height="610"
          />
          <div class="carousel-caption">
            <h1>
              Fortune
              <span class="text-danger">Cookies</span>
            </h1>
            <h3>Crack open your fortune cookie</h3>
          </div>
        </div>
        <div class="carousel-item">
          <img
            src="/images/bowl-of-cookies-slider-2.jpg"
            class="d-block w-100 mh-100"
            alt="Chicago"
            height="610"
          />
          <div class="carousel-caption">
            <h1>FORTUNES</h1>
            <h3>Be prepared to accept your fortune</h3>
          </div>
        </div>
      </div>

      <!-- Left and right controls -->
      <a class="carousel-control-prev" href="#demo" data-slide="prev">
        <span class="carousel-control-prev-icon"></span>
      </a>
      <a class="carousel-control-next" href="#demo" data-slide="next">
        <span class="carousel-control-next-icon"></span>
      </a>
    </div>
  </div>
</template>
<style scoped>
.carousel-caption {
  position: absolute;
  top: 50%;
  left: 50%;
  z-index: 3;
  color: #fff;
  width: 100%;
  text-align: center;
  text-transform: uppercase;
  text-shadow: 1px 1px 0 rgba(0, 0, 0, 0.75);
  -webkit-transform: translate3d(-50%, -50%, 0);
  -moz-transform: translate3d(-50%, -50%, 0);
  -ms-transform: translate3d(-50%, -50%, 0);
  -o-transform: translate3d(-50%, -50%, 0);
  transform: translate3d(-50%, -50%, 0);
}
.carousel-caption h1 {
  font-size: 4em;
  margin: 0;
  padding: 0;
}
.carousel-fade .carousel-inner .carousel-item .carousel-caption {
  opacity: 0;
  -webkit-transition: 0.2s all ease-in-out 0.1s;
  -moz-transition: 0.2s all ease-in-out 0.1s;
  -ms-transition: 0.2s all ease-in-out 0.1s;
  -o-transition: 0.2s all ease-in-out 0.1s;
  transition: 0.2s all ease-in-out 0.1s;
}
.carousel-fade .carousel-inner .carousel-item.active .carousel-caption {
  opacity: 1;
  -webkit-transition: 0.5s all ease-in-out 0.1s;
  -moz-transition: 0.5s all ease-in-out 0.1s;
  -ms-transition: 0.5s all ease-in-out 0.1s;
  -o-transition: 0.5s all ease-in-out 0.1s;
  transition: 0.5s all ease-in-out 0.1s;
}
</style>
