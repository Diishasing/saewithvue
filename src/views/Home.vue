<template>
  <main>
    <div id="fb-root"></div>
    <div class="bd-example">
      <div
        id="carouselExampleCaptions"
        class="carousel slide"
        data-ride="carousel"
      >
        <ol class="carousel-indicators">
          <li
            data-target="#carouselExampleCaptions"
            v-for="(image, index) in carouselImage"
            :key="index"
            :data-slide-to="index - 1"
          ></li>
        </ol>
        <div class="carousel-inner">
          <div
            class="carousel-item"
            v-for="(image, index) in carouselImage"
            :key="index"
            :class="[index === 0 ? 'active' : '']"
          >
            <picture>
              <source
                type="image/webp"
                v-lazy="require(`@/assets/images/carousel/${image}.webp`)"
              />
              <img
                class="d-block w-100"
                :src="require(`@/assets/images/carousel/${image}.jpg`)"
                alt="zfr"
              />
            </picture>
          </div>
        </div>
      </div>
    </div>

    <section id="main_image">
      <header id="header_text">
        <p><span>Z</span>HCET</p>
        <p><span>F</span>ormula <span>R</span>acing</p>
      </header>
    </section>
    <section id="description-zfr">
      <header class="some-headings">About Zhcet Formula Racing</header>
      <article class="about-text">
        ZHCET FORMULA RACING is a formula racing team of 40 quite hard working
        and passionate undergraduate engineering students from Aligarh Muslim
        University who ideate, design, fabricate and test a formula style race
        car and participate in various National as well as International formula
        student competitions.
      </article>
    </section>
    <section id="social-block">
      <div>
        <div class="some-headings">Social media updates</div>
      </div>
      <div id="page-container">
        <!-- <div class="first">
          <div id="insta-container">
            <iframe
              src="//lightwidget.com/widgets/a783dbf4dca95e0ea5eec31e206ec03f.html"
              allowtransparency="true"
              class="lightwidget-widget"
              style="width:100%;height:500px;border:0;overflow:hidden;"
            ></iframe>
          </div>
        </div>-->
        <div class="second">
          <div id="fb-page12">
            <div
              class="fb-page"
              data-href="https://www.facebook.com/ZHCETFormulaRacing/"
              data-tabs="timeline"
              data-width="500"
              data-height="500"
              data-small-header="true"
              data-adapt-container-width="true"
              data-hide-cover="true"
              data-show-facepile="true"
            >
              <blockquote
                cite="https://www.facebook.com/ZHCETFormulaRacing/"
                class="fb-xfbml-parse-ignore"
              >
                <a
                  style="color:indianred"
                  target="_blank"
                  href="https://www.facebook.com/ZHCETFormulaRacing/"
                >
                  Facebook page Loading
                  <svg
                    width="30"
                    height="30"
                    viewBox="0 0 57 57"
                    xmlns="http://www.w3.org/2000/svg"
                    stroke="black"
                  >
                    <g fill="indianred" fill-rule="evenodd">
                      <g transform="translate(1 1)" stroke-width="2">
                        <circle cx="5" cy="50" r="5">
                          <animate
                            attributeName="cy"
                            begin="0s"
                            dur="2.2s"
                            values="50;5;50;50"
                            calcMode="linear"
                            repeatCount="indefinite"
                          />
                          <animate
                            attributeName="cx"
                            begin="0s"
                            dur="2.2s"
                            values="5;27;49;5"
                            calcMode="linear"
                            repeatCount="indefinite"
                          />
                        </circle>
                        <circle cx="27" cy="5" r="5">
                          <animate
                            attributeName="cy"
                            begin="0s"
                            dur="2.2s"
                            from="5"
                            to="5"
                            values="5;50;50;5"
                            calcMode="linear"
                            repeatCount="indefinite"
                          />
                          <animate
                            attributeName="cx"
                            begin="0s"
                            dur="2.2s"
                            from="27"
                            to="27"
                            values="27;49;5;27"
                            calcMode="linear"
                            repeatCount="indefinite"
                          />
                        </circle>
                        <circle cx="49" cy="50" r="5">
                          <animate
                            attributeName="cy"
                            begin="0s"
                            dur="2.2s"
                            values="50;50;5;50"
                            calcMode="linear"
                            repeatCount="indefinite"
                          />
                          <animate
                            attributeName="cx"
                            from="49"
                            to="49"
                            begin="0s"
                            dur="2.2s"
                            values="49;5;27;49"
                            calcMode="linear"
                            repeatCount="indefinite"
                          />
                        </circle>
                      </g>
                    </g>
                  </svg>
                </a>
              </blockquote>
            </div>
          </div>
        </div>
      </div>
      <div id="youtube-box">
        <div @click="Iframe()" id="youtube-player">
          <div v-if="!video" data-id="q6yPVslIujk">
            <img
              id="thumbnail"
              src="https://i.ytimg.com/vi/q6yPVslIujk/hqdefault.jpg"
              alt="yotube videos' thumbnail"
            />
            <div class="play"></div>
          </div>
          <iframe
            v-if="video"
            src="https://www.youtube.com/embed/B36d2OTvtKI"
            frameborder="0"
            allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture"
            allowfullscreen
          ></iframe>
        </div>
      </div>
    </section>
    <section class="grid-view">
      <div class="parts">
        <section
          class="wrapper"
          v-for="(item, index) in details"
          :key="index"
          :class="[index === 1 ? 'alter-grid' : '']"
        >
          <div class="grid-text">
            <div class="icon">
              <figure>
                <img
                  :src="require(`@/assets/icons/home_icons/${item.icon}`)"
                  alt="icon"
                />
              </figure>
            </div>
            <header class="heading-text">{{ item.heading }}</header>
            <article class="body-text">{{ item.body }}</article>
            <div class="link">
              <router-link :to="{ name: `${item.link}` }">
                <span>
                  Know more
                  <img
                    :src="
                      require('@/assets/icons/home_icons/chevron-solid.svg')
                    "
                    class="chevron-solid"
                    :alt="`arrow to ${item.heading} page`"
                  />
                </span>
              </router-link>
            </div>
          </div>
          <div class="grid-image">
            <div class="image-container">
              <picture>
                <source
                  type="image/webp"
                  v-lazy="require(`@/assets/images/home_images/${item.webp}`)"
                />
                <img
                  :src="require(`@/assets/images/home_images/${item.image}`)"
                  alt="zfr"
                />
              </picture>
            </div>
          </div>
        </section>
      </div>
    </section>

    <section>
      <TheForm />
    </section>
  </main>
</template>
<script>
import TheForm from "@/components/TheForm.vue";
export default {
  components: {
    TheForm
  },
  data() {
    return {
      v: null,
      video: false,
      carouselImage: ["0","5","4","3","2"],
      details: [
        {
          icon: "flag.png",
          heading: "Formula Student",
          body: `Being one of the most prestigious design competitions round the globe, formula
              student is a global showdown which challenges the university undergraduates to combine hands on practical
              appliances along with project management skills.`,
          link: "FS",
          image: "formulastudent.jpg",
          webp: "formulastudent.webp"
        },
        {
          icon: "car.png",
          heading: "Our Cars",
          body: `Till now our club has made 5 cars out of which ZFR5.0 is latest and we are working on
              ZFR-EV, ZFR 6.0 and other future projects.`,
          link: "Cars",
          image: "collage.jpg",
          webp: "collage.webp"
        },
        {
          icon: "mechanic.png",
          heading: "Our Crew",
          body:
            "Meet the students of AMU, who are working day and night to make ZFR better.",
          image: "team.jpeg",
          webp: "team.webp",
          link: "Crew"
        }
      ]
    };
  },
  mounted() {
    let scriptAdder = document.createElement("script");
    scriptAdder.setAttribute(
      "src",
      "https://connect.facebook.net/en_GB/sdk.js#xfbml=1&version=v4.0"
    );
    scriptAdder.setAttribute("crossorigin", "anonymous");
    scriptAdder.setAttribute("async", "");
    document.head.appendChild(scriptAdder);
  },
  methods: {
    Iframe() {
      this.video = true;
    }
  }
};
</script>

<style scoped>
body {
  overflow-x: hidden;
}

#description-zfr {
  margin-top: 6%;
}

.chevron-solid {
  height: 20px;
  width: 20px;
}

#main_image {
  position: absolute;
  top: 0;
  width: 100%;
}

#header_text {
  background: rgba(0, 0, 0, 0.5);
  color: rgb(255, 255, 255);
  font-size: 20vw;
  font-family: Cinzel;
  font-weight: 800;
  height: 100vh;
  padding-top: 28vh;
  text-shadow: black 5px 5px 5px;
}

#wrapper {
  position: relative;
  height: 100vh;
  overflow: hidden;
}
blockquote {
  text-align: center;
}
blockquote svg {
  position: relative;
  top: 5px;
}
.bd-example {
  margin-top: 68.25px;
  position: relative;
  z-index: 0;
  width: 100%;
}

.carousel-item img {
  height: calc(100vh - 68.25px);
}

.about-text {
  padding: 5%;
  font-size: 1.4em;
  text-align: justify;
  line-height: 1.8;
  width: 80%;
  font-family: "Open Sans";
  margin: auto;
  min-width: 300px;
  color: #414042;
}

p {
  margin: auto;
  width: fit-content;
  text-align: center;
  border-left: 3px solid goldenrod;
  padding-left: 2%;
}

.parts {
  display: grid;
  grid-template-columns: 1fr;
  min-height: 200px;
}

.wrapper {
  display: grid;
  grid-template-columns: 1fr 1fr;
  min-height: 200px;
  grid-column-gap: 5%;
  grid-template-areas: "second first";
}

.wrapper .heading-text {
  font: 500 2.3em Domine;
}

.parts section {
  border-top: 2px solid goldenrod;
  margin-top: 50px;
  padding: 50px 0;
}

.grid-view {
  margin: 50px 5%;
  font-family: "Open Sans";
}

.grid-text {
  width: 100%;
  min-height: 400px;
  padding: 2.2em 0;
}

.grid-text > div {
  margin: 3%;
  margin-left: 0;
}
article {
  margin: 3% 0;
}
.grid-text .body-text {
  text-align: justify;
  font-family: "Open Sans";
  font-size: 1.4em;
  line-height: 1.6;
  color: #414042;
}

.grid-text .link {
  text-decoration: none;
  font-size: 1.4em;
  text-align: left;
}
.link span {
  color: #333;
}

.icon div {
  background: rgb(245, 244, 244);
  height: 50px;
  width: 50px;
  border-radius: 50%;
}

.icon img {
  height: 50px;
  width: 50px;
}

.grid-image {
  display: flex;
  align-items: center;
}

.grid-image {
  padding: 12px;
}

.grid-image .image-container img {
  height: calc(60vw * (562 / 1000));
  min-height: 200px;
  max-height: 400px;
  border-radius: 12px;
  box-shadow: 0 2px 6px 3px rgba(0, 0, 0, 0.32);
  width: 100%;
  display: block;
  margin: auto;
}

#page-container {
  display: grid;
  margin: 5%;
  padding-top: 0;
  grid-template-columns: 1fr;
  /* grid-column-gap: 5%; */
}

#fb-page12 {
  max-width: 500px;
  width: 50vw;
  margin: auto;
}

#social-block .some-headings {
  margin: 5% 0;
  padding: 3rem 0;
  background-color: indianred;
  position: relative;
}
#social-block .some-headings::after,
#social-block .some-headings::before {
  content: "";
  position: absolute;
  background-color: indianred;
  height: 45px;
  width: 10.4%;
  bottom: -9px;
}
#social-block .some-headings::before {
  left: 50%;
  transform: translateX(-100%) skewY(12deg);
}
#social-block .some-headings::after {
  right: 50%;
  transform: translateX(99%) skewY(-12deg);
}

.some-headings {
  text-align: center;
  font: 600 2.59em Domine;
  padding: 30px 5%;
}

.alter-grid .grid-image {
  grid-area: second;
}

.alter-grid .grid-text {
  grid-area: first;
}

#insta-container iframe {
  margin: auto;
  /* see the details inside the iframe */
}

#youtube-box {
  margin: 100px 8%;
  overflow: hidden;
  background: indianred;
}

#youtube-player {
  width: fit-content;
  margin: auto;
  /* padding: 8px; */
  position: relative;
}

#youtube-player iframe {
  margin: auto;
  display: block;
  width: 75vw;
  min-width: 280px;
  min-height: 200px;
  height: calc(75vw * (562 / 1000));
}
#youtube-player > div {
  width: 75vw;
  min-width: 280px;
  min-height: 200px;
  height: calc(75vw * (562 / 1000));
}
#youtube-player img {
  display: block;
  margin: auto;
  position: absolute;
  top: -17%;
  height: 134%;
  width: 100%;
  border: none;
  cursor: pointer;
  -webkit-transition: 0.4s all;
  -moz-transition: 0.4s all;
  transition: 0.4s all;
}

#youtube-player img:hover {
  -webkit-filter: brightness(75%);
}

#youtube-player .play {
  width: 72px;
  height: 72px;
  left: 50%;
  top: 50%;
  transform: translate(-50%, -50%);
  position: absolute;
  background: url("https://i.imgur.com/TxzC70f.png") no-repeat;
  cursor: pointer;
}

@media screen and (min-width: 700px) {
  #header_text {
    font-size: 9vw;
  }
}

@media screen and (max-width: 767px) {
  #social-block .some-headings::after,
  #social-block .some-headings::before {
    content: "";
    position: absolute;
    background-color: indianred;
    height: 30px;
    width: 10%;
    min-width: 50px;
    bottom: -3px;
  }
  .wrapper {
    display: grid;
    grid-template-columns: 1fr;
    min-height: 200px;
    grid-column-gap: 30px;
  }
  #social-block .some-headings {
    margin: 8% 0;
    padding: 8% 0;
    background-color: indianred;
  }
  #fb-page12 {
    width: 85vw;
    margin: auto;
    margin-top: 10vh;
  }

  #page-container {
    grid-template-columns: 1fr;
  }
  .grid-text {
    padding: 1.6em 1em;
  }
  .grid-text > * {
    padding: 12px 0;
  }
  .grid-text .body-text,
  .about-text {
    font-size: 1.05em;
  }

  .some-headings,
  .wrapper .heading-text {
    margin-top: 20px;
    font-size: 1.8em;
  }

  .wrapper {
    grid-template-columns: 1fr;
    grid-template-areas:
      "first"
      "second";
  }
  .bd-example {
    margin-top: 56px;
  }
  .carousel-item img {
    height: calc(100vh - 56px);
  }
}
</style>
