<template>
  <main id="main">
    <div id="cars-index">
      <!-- header -->
      <section id="cars-head">
        <div class="text-block">
          <h1>OUR RACING CARS</h1>
        </div>
      </section>
      <!-- End of header -->

      <!-- Cars of Sae Zhcet -->
      <!-- <div class="container"> -->
      <section id="cars-sae">
        <div class="row">
          <div class="col-md-6 col-sm-12" v-for="car in cars" :key="car.id">
            <div class="image-box">
              <router-link
                :to="{ name: 'CarModel', params: { carName: car.name } }"
              >
                <img
                  v-lazy="require(`@/assets/images/car_images/${car.image}`)"
                />
              </router-link>
            </div>
            <div class="name name-center">
              <router-link
                :to="{ name: 'CarModel', params: { carName: car.name } }"
              >
                <h2>{{ car.name }}</h2>
              </router-link>
            </div>
          </div>
          <div class="col-md-6 col-sm-12">
            <div class="image-box">
              <div>
                <img
                  v-lazy="
                    require(`@/assets/images/car_images/${upcomingCar.image}`)
                  "
                />
              </div>
            </div>
            <div class="name name-center">
              <div>
                <h2>{{ upcomingCar.name }}</h2>
              </div>
            </div>
          </div>
        </div>
      </section>
      <!-- </div> -->
      <!-- End of cars of Sae Zhcet -->
      <div class="container">
        <h2 class="text-block">Gold Sponsors</h2>
        <div class="row sponsor">
          <div
            class="col-md-6"
            v-for="(sponsor, index) in sponsors"
            :key="index"
          >
            <img v-lazy="sponsor" width="100%" height="100%" />
          </div>
        </div>
      </div>

      <div v-if="screenSize" id="sidecar" :style="car">
        <img src="../assets/images/car_images/car.png" alt />
      </div>
      <div v-if="screenSize" id="sidecar-path">
        <img id="path" src="../assets/images/car_images/path.jpg" alt />
      </div>
    </div>
  </main>
</template>

<script>
export default {
  mounted() {
    this.carAnimation();
    this.bodyHeight = document.getElementById("cars-index").clientHeight;
    document.getElementById("path").style.height = this.bodyHeight;
    document.addEventListener("scroll", this.carAnimation);
  },
  beforeDestroy() {
    document.removeEventListener("scroll", this.carAnimation);
  },
  methods: {
    carAnimation() {
      var cScrollPos = window.pageYOffset;
      if (cScrollPos < this.bodyHeight + 100) {
        this.distance += cScrollPos - this.pScrollpos;
        if (document.getElementById("sidecar")) {
          if (cScrollPos < this.pScrollpos) {
            document.getElementById("sidecar").style.transform =
              "rotate(270deg)";
          } else {
            document.getElementById("sidecar").style.transform =
              "rotate(90deg)";
          }
        }
        this.pScrollpos = cScrollPos;
      }
      this.car = { top: this.distance + "px" };
    }
  },
  data() {
    return {
      distance: 200,
      bodyHeight: null,
      pScrollpos: 0,
      car: null,
      screenSize: [screen.width > 1023 ? true : false],
      cars: [
        {
          image: "zfr1.jpg",
          id: 1,
          name: "ZFR 1.0",
          link: "cars/zfr-1"
        },
        {
          image: "zfr2.jpg",
          link: "cars/zfr-2",
          name: "ZFR 2.0",
          id: 2
        },
        {
          image: "zfr3.jpg",
          link: "cars/zfr-3",
          name: "ZFR 3.0",
          id: 3
        },
        {
          image: "zfr4.jpg",
          link: "cars/zfr-4",
          name: "ZFR 4.0",
          id: 4
        },
        {
          image: "zfr4.1.jpg",
          link: "cars/zfr-4.1",
          name: "ZFR 4.1",
          id: 5
        }
      ],
      upcomingCar: {
        image: "0.jpg",
        link: "cars/zfr-5.0",
        name: "ZFR 5.0",
        id: 6
      },
      sponsors: [
        "https://www.marshall.edu/it/files/mathworks-logo.jpg",
        "https://yt3.ggpht.com/a/AGF-l79atE0GzZ5jy-Fmio_r6gz6xdXY3N4NwPb8Og=s900-c-k-c0xffffffff-no-rj-mo",
        "http://alwafagroupuae.com/Alwafa-Dashboard/uploads/clients/efs%20logo.png",
        "https://images.ipros.jp/public/company/image/89b/2046702/IPROS29723033195651003817.png?w=220&h=220"
      ]
    };
  }
};
</script>

<style scoped>
#cars-index {
  background-color: #cccccc; /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */
}

main,
main > div {
  position: relative;
  padding: 1px 0;
}
.text-block {
  color: white;
  text-align: center;
  background-color: black;
}
h2.text-block {
  padding: 12px;
}
.text-block h1 {
  font-family: "Open Sans";
  font-size: 400%;
  cursor: default;
}
#cars-head {
  margin-top: 56px;
  position: relative;
  z-index: 1;
  background-color: #000;
  margin-bottom: 2%;
}
.image-box {
  text-align: center;
}
.image-box img {
  width: 50%;
}
.spec img {
  height: 63vh;
  width: 56%;
}

.row,
.col-md-6 {
  padding: 1%;
  margin-bottom: 5%;
  max-width: 100vw !important;
}
.sponsor .col-md-6 {
  margin-bottom: 0px;
  height: 50vh;
  padding: 2%;
}
.sponsor .col-md-6 img {
  box-shadow: 0 0 12px 0 black;
  /* transform: rotateY(80deg) rotateZ(-25deg) ; */
}
.name-center {
  background-color: white;
  color: black;
}
.name {
  text-align: center;
  margin: auto;
  padding: 12px;
  margin-bottom: 5%;
  width: 50%;
}
.name h1 {
  text-decoration: none;
  cursor: default;
  margin-top: 2%;
  font-weight: 600;
}
.name a {
  text-decoration: none;
  /* color: white; */
}
.name a h2,
.name div h2 {
  font-size: 2.2em;
  font-weight: bolder;
  color: #000;
}

.col-md-6 h1 {
  text-align: center;
  font-size: 2.2em;
}

table {
  font-family: arial, sans-serif;
  border-collapse: collapse;
  width: 100%;
}

td,
th {
  border: 1px solid #dddddd;
  text-align: left;
  padding: 2.5%;
  /* overflow-wrap: break-word; */
}
tr:nth-child(even) {
  background-color: #ddd;
}
.col-md-12 {
  padding: 0;
}

.col-sm-12 {
  padding: 4%;
}
.col-sm-12 h1 {
  font-size: 2.2em;
  text-align: center;
}
.points li {
  padding: 0.4%;
  margin-left: 5%;
}
#sidecar {
  position: absolute;
  z-index: 1;
  transform: rotate(90deg);
  right: 30px;
  top: 100px;
  transition: top 0.5s ease-out;
  visibility: hidden;
}

#sidecar-path {
  position: absolute;
  top: 50px;
  right: 32px;
  z-index: 0;
  border: 2px solid white;
  visibility: hidden;
}
#sidecar-path img {
  visibility: hidden;
  height: 500px;
  width: 55px;
}

@media (max-width: 500px) {
  .text-block h1 {
    font-size: 10vw;
  }
  .spec img {
    width: 80%;
  }
  #cars-sae .row {
    margin: 0;
  }
  #cars-sae .col-md-6 img,
  #cars-sae .col-md-6 .name-center {
    width: 90% !important;
  }
}
@media (min-width: 500px) and (max-width: 768px) {
  .text-block h1 {
    font-size: 9vw;
  }
}
@media screen and (min-width: 1024px) {
  #sidecar,
  #sidecar-path,
  #sidecar-path img {
    visibility: visible;
  }
  #sidecar-path img {
    height: 2400px;
  }
  #cars-head {
    margin-top: 64px;
  }
}
@media screen and (min-width: 1024px) and (max-width: 1100px) {
  .container {
    width: 125vh;
  }
}

@media screen and (min-width: 1198px) {
  .container {
    width: 150vh;
  }
  #sidecar-path img {
    height: 2500px;
  }
}
</style>
