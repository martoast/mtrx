<template>
  <b-container>
    <b-navbar toggleable="lg" type="dark" style="background-color: #000000">
      <b-navbar-brand href="#">
        <img
          src="/images/small-logo.svg"
          class="d-inline-block align-top"
          alt="logo "
        />
      </b-navbar-brand>

      <b-navbar-toggle
        style="border-color: transparent; color: white"
        class="text-white"
        target="nav-collapse"
      ></b-navbar-toggle>

      <b-collapse id="nav-collapse" is-nav>
        <b-navbar-nav>
          <b-nav-item active style="font-weight: 600" href="#">
            Tech
          </b-nav-item>
          <b-nav-item active style="font-weight: 600" href="#">
            Metaverse
          </b-nav-item>
          <b-nav-item active style="font-weight: 600" href="#">
            News
          </b-nav-item>
        </b-navbar-nav>
      </b-collapse>
    </b-navbar>

    <div
      style="
        border-radius: 20px;
        margin-bottom: 30px;
        margin-top: 18px;
        overflow: hidden;
        position: relative;
      "
    >
      <div v-if="!play_video">
        <b-img-lazy
          src="/images/header.png"
          fluid
          style="position: relative; max-height: 592px; width: 100%"
        >
        </b-img-lazy>
        <b-button
          style="
            position: absolute;
            bottom: 49%;
            left: 35%;
            background-color: rgba(7, 252, 252, 1);
          "
          size="lg"
          @click="onplayVideo"
        >
          <b-icon icon="play-fill" scale="2"> </b-icon>
        </b-button>
      </div>

      <div v-else>
        <video
          style="100%"
          width="100%"
          autoplay
          muted
          controls
          playsinline
          webkit-playsinline
        >
          <source src="/videos/mainvideo.mp4" type="video/mp4" preload="auto" />
          Your browser does not support video
        </video>
      </div>
    </div>

    <div
      style="
        border-radius: 42px;
        background-image: url('/images/main-gradient.png'); /* The image used */
        height: 100%; /* You must set a specified height */
        background-position: center; /* Center the image */
        background-repeat: no-repeat; /* Do not repeat the image */
        background-size: cover; /* Resize the background image to cover the entire container */
      "
    >
      <b-row class="pb-5 p-3" align-v="center">
        <b-col cols="12" md="6" sm="12">
          <div class="p-2">
            <b-img-lazy
              style="border-radius: 300px; max-height: 418px; width: 590px"
              src="/images/pool.jpg"
              fluid
              alt="Responsive image"
            ></b-img-lazy>
          </div>
        </b-col>
        <b-col class="pt-3" cols="12" md="6" sm="12">
          <h2 class="pb-3" style="font-weight: 800; color: #43ee9c">
            A METAVERSE MADE FOR THE ARTIST, BY ARTISTS.
          </h2>
          <h2 class="text-white" style="font-weight: 800">
            BE THE FIRST TO KNOW
          </h2>
          <h2 class="text-white pb-3" style="font-weight: 800; font-size: 30px">
            SIGN UP NOW
          </h2>

          <h4 class="text-white pb-3" id="timer"></h4>

          <b-form inline @submit="onSubmit" @reset="onReset">
            <b-form-input
              style="background-color: transparent; border-color: #6e0095"
              id="input-1"
              v-model="form.email"
              :state="emailState"
              type="email"
              placeholder="EMAIL"
              required
            ></b-form-input>

            <b-button
              :disabled="!emailState"
              class="d-none d-md-block ml-3"
              style="background-color: #00c0f9; border-color: #00c0f9"
              >ENTER THE MTRX
            </b-button>

            <b-button
              :disabled="!emailState"
              class="d-block d-md-none mt-3"
              style="background-color: #00c0f9; border-color: #00c0f9"
              >Enter the MTRX
            </b-button>
          </b-form>
        </b-col>
      </b-row>
      <div class="pb-5">
        <b-card
          no-body
          class="text-white align-items-center p-3"
          style="border-radius: 100px; background: rgba(94, 94, 94, 0.5)"
        >
          <b-row align-v="center" align-h="center" class="py-4 w-100">
            <b-col class="ml-md-auto" cols="12" md="6" sm="12">
              <h2
                style="
                  font-weight: 800;
                  color: rgba(67, 238, 156, 1);
                  margin: 0px;
                "
              >
                IT’S YOUR WORLD
              </h2>
              <h2
                style="
                  font-weight: 800;
                  color: rgba(67, 238, 156, 1);
                  margin: 0px;
                "
                class="pb-3"
              >
                AND ITS YOUR STAGE
              </h2>

              <p class="pb-2">
                Welcome to the MTRXVerse, the ultimate talent and performance
                Metaverse built by actual music industry artists to help
                creators share their world with the world; no matter the
                location. From fully customizable performance stages, to fashion
                airdrops, to brand sponsored immersive activations, to full on
                music festivals with custom effects the MTRXVERSE is the
                ultimate home for the next generation of artists to directly
                connect with their fans around the globe in a whole new way. You
                no longer have to BE THERE to BE THERE. Enter the MTRXVerse
              </p>
              <b-button
                pill
                class="border-0"
                style="background-color: #00c0f9; border-color: #00c0f9"
                >LEARN MORE</b-button
              >
            </b-col>

            <b-col class="ml-auto py-3" cols="12" md="4" sm="12">
              <b-img-lazy
                src="/images/banner-logo.svg"
                fluid
                alt="Fluid image"
              ></b-img-lazy>
            </b-col>
          </b-row>
        </b-card>
      </div>

      <div class="pb-5 text-white">
        <b-img-lazy
          fluid
          class="pb-1 center-img"
          style="max-width: 250px"
          src="/images/metafest.svg"
        ></b-img-lazy>
        <h2 class="text-center" style="font-weight: 800; color: #43ee9c">
          ROADMAP
        </h2>

        <b-img-lazy
          class="center-img d-none d-md-block"
          src="/images/timeline.png"
          fluid-grow
          alt="roadmap-image"
          style="padding-right: 3rem"
        ></b-img-lazy>
        <b-img-lazy
          class="center-img d-block d-md-none"
          src="/images/timeline.png"
          fluid-grow
          alt="roadmap-image"
          style="padding-right: 1rem"
        ></b-img-lazy>
      </div>
      <div class="pb-5">
        <b-img-lazy
          fluid
          src="/images/metamansion.png"
          class="center-img"
        ></b-img-lazy>

        <b-carousel
          id="carousel-1"
          v-model="slide"
          :interval="4000"
          controls
          indicators
          background="#ababab"
          style="text-shadow: 1px 1px 2px #333"
          @sliding-start="onSlideStart"
          @sliding-end="onSlideEnd"
        >
          <b-carousel-slide img-src="/images/metaweek.png"> </b-carousel-slide>

          <!-- Slides with image only -->
          <b-carousel-slide img-src="/images/metaweek.png"></b-carousel-slide>

          <b-carousel-slide img-src="/images/metaweek.png"></b-carousel-slide>
        </b-carousel>
      </div>
    </div>

    <h2 class="text-center text-white py-3" style="font-weight: 800">NEWS</h2>
    <b-card-group class="p-3" deck>
      <b-card
        v-for="item in news"
        :key="item.id"
        style="background-color: #07fcfc !important"
        no-body
      >
        <div class="p-1">
          <b-card-img class="blog-img" :src="item.image" alt="Image">
          </b-card-img>
          <a
            :href="item.link"
            style="
              position: absolute;
              z-index: 10000;
              right: 2rem;
              top: 1rem;
              color: #07fcfc;
            "
            ><b-icon scale="2" icon="arrow-right"></b-icon
          ></a>

          <b-card-title class="pt-2" style="height: 94px">
            {{ item.title }}
          </b-card-title>
          <b-card-text style="height: 96px">
            {{ item.content }}
          </b-card-text>
          <b-button :href="item.link" variant="light">Read more</b-button>
        </div>
      </b-card>
    </b-card-group>

    <div
      class="pt-5"
      style="
        border-radius: 42px;
        background-image: url('/images/news.png'); /* The image used */
        height: 100%; /* You must set a specified height */
        background-position: center; /* Center the image */
        background-repeat: no-repeat; /* Do not repeat the image */
        background-size: cover; /* Resize the background image to cover the entire container */
      "
    >
      <div class="pb-5 mt-5">
        <b-card
          no-body
          class="text-white align-items-center"
          style="background-color: transparent"
        >
          <div class="p-4">
            <h2
              class="text-center text-white"
              style="font-weight: 800; margin: 0px"
            >
              POWERED BY
            </h2>

            <h2
              class="text-center text-white"
              style="font-weight: 800; margin: 0px"
            >
              KLAYTN
            </h2>

            <b-row align-v="center" align-h="center" class="py-4 w-100">
              <b-col class="ml-md-auto" cols="12" md="6" sm="12">
                <p style="font-weight: 700; font-size: 22px">
                  Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed
                  do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                  Ut enim ad minim veniam, quis nostrud exercitation ullamco
                  laboris nisi ut aliquip ex ea commodo consequat. Duis aute
                  irure dolor in reprehenderit in voluptate velit esse cillum
                  dolore
                </p>
              </b-col>

              <b-col class="ml-auto" cols="12" md="4" sm="12">
                <b-img-lazy
                  src="/images/klaytn.png"
                  style="max-width: 300px"
                  fluid
                  alt="Fluid image"
                ></b-img-lazy>
              </b-col>
            </b-row>
          </div>
        </b-card>
      </div>
    </div>

    <b-container class="py-5">
      <b-row align-v="center">
        <b-col col md="5" sm="12">
          <div class="d-flex">
            <div>
              <b-img-lazy
                class="pb-3"
                src="/images/footerlogo.svg"
              ></b-img-lazy>
              <p
                class="text-white pb-3"
                style="font-weight: 700; font-size: 24px"
              >
                The Bridge Between Metaverse and IRL Events.
              </p>
            </div>
            <div>
              <b-list-group>
                <b-list-group-item
                  href="#"
                  class="border-0 text-white"
                  style="background-color: transparent"
                >
                  Tech
                </b-list-group-item>

                <b-list-group-item
                  href="#"
                  class="border-0 text-white"
                  style="background-color: transparent"
                >
                  Metaverse
                </b-list-group-item>

                <b-list-group-item
                  href="#"
                  class="border-0 text-white"
                  style="background-color: transparent"
                >
                  News
                </b-list-group-item>
              </b-list-group>
            </div>
          </div>
        </b-col>
        <b-col col md="7" sm="12">
          <h1
            class="text-white text-center pb-3"
            style="
              font-weight: 700;
              font-size: 43px;
              text-decoration: underline;
            "
          >
            ENTER THE MTRX
          </h1>
          <b-form
            style="justify-content: center"
            inline
            @submit="onSubmit"
            @reset="onReset"
          >
            <b-form-input
              style="background-color: transparent; border-color: #6e0095"
              id="input-1"
              v-model="form.email"
              :state="emailState"
              type="email"
              placeholder="EMAIL"
              required
            ></b-form-input>

            <b-button
              :disabled="!emailState"
              class="d-none d-md-block ml-3"
              style="background-color: #00c0f9; border-color: #00c0f9"
              >ENTER THE MTRX
            </b-button>

            <b-button
              :disabled="!emailState"
              class="d-block d-md-none mt-3"
              style="background-color: #00c0f9; border-color: #00c0f9"
              >Enter the MTRX
            </b-button>
          </b-form>
        </b-col>
      </b-row>
    </b-container>

    <div class="d-none d-md-flex justify-content-center">
      <b-btn variant="link">
        <b-img-lazy src="/images/social/youtube.svg" fluid></b-img-lazy>
      </b-btn>
      <b-btn variant="link">
        <b-img-lazy src="/images/social/facebook.svg"></b-img-lazy>
      </b-btn>
      <b-btn variant="link">
        <b-img-lazy src="/images/social/twitter.svg"></b-img-lazy>
      </b-btn>
      <b-btn variant="link">
        <b-img-lazy src="/images/social/twitch.svg"></b-img-lazy>
      </b-btn>
      <b-btn variant="link">
        <b-img-lazy src="/images/social/instagram.svg"></b-img-lazy>
      </b-btn>
      <b-btn variant="link">
        <b-img-lazy src="/images/social/discord.svg"></b-img-lazy>
      </b-btn>
    </div>
  </b-container>
</template>

<script>
export default {
  name: "IndexPage",
  layout: "main",

  data() {
    return {
      play_video: false,

      form: {
        email: "",
      },
      news: [
        {
          id: 1,
          title: "AP Photos Diplo Hamptons Party",
          subtitle: "subtitle",
          image: "/images/blog1.png",
          link: "https://bit.ly/APNewsMtrx",
          content:
            "Enjoy all the photos by AP images of our latest metamansion takeover. ",
        },
        {
          id: 2,
          title: "Parties take over the Hamptons for Fourth of July weekend",
          subtitle: "subtitle",
          image: "/images/blog2.png",
          link: "https://bit.ly/PageSixMtrx",
          content:
            "Over the Fourth of July holiday weekend, hospitality guru Richie Akiva and Ronnie Madra threw a bash at Kissaki in Water Mill.",
        },
        {
          id: 3,
          title: "title of the blog",
          subtitle: "subtitle",
          image:
            "https://i.picsum.photos/id/41/300/300.jpg?hmac=btJpFIxxGUDXvakI9MK1mRAP0Mmwhgk_o34Ps2vkhxA",
          link: "https://bit.ly/PageSixMtrx",
          content:
            "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. ",
        },
      ],
      slide: 0,
      sliding: null,
    };
  },
  mounted() {
    // Set the date we're counting down to
    var countDownDate = new Date("Jan 5, 2024 15:37:25").getTime();

    // Update the count down every 1 second
    var x = setInterval(function () {
      // Get today's date and time
      var now = new Date().getTime();

      // Find the distance between now and the count down date
      var distance = countDownDate - now;

      // Time calculations for days, hours, minutes and seconds
      var days = Math.floor(distance / (1000 * 60 * 60 * 24));
      var hours = Math.floor(
        (distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60)
      );
      var minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
      var seconds = Math.floor((distance % (1000 * 60)) / 1000);

      // Display the result in the element with id="demo"
      document.getElementById("timer").innerHTML =
        days + "d " + hours + "h " + minutes + "m " + seconds + "s ";

      // If the count down is finished, write some text
      if (distance < 0) {
        clearInterval(x);
        document.getElementById("timer").innerHTML = "EXPIRED";
      }
    }, 1000);
  },
  computed: {
    emailState() {
      if (this.form.email) {
        if (
          /^\w+([\.-]?\w+)*@\w+([\.-]?\w+)*(\.\w{2,3})+$/.test(this.form.email)
        ) {
          return true;
        }

        return false;
      }
    },
  },
  methods: {
    onplayVideo() {
      this.play_video = true;
    },
    onSubmit(event) {
      event.preventDefault();
      alert(JSON.stringify(this.form));
    },
    onReset(event) {
      event.preventDefault();
      // Reset our form values
      this.form.email = "";
    },
    onSlideStart(slide) {
      this.sliding = true;
    },
    onSlideEnd(slide) {
      this.sliding = false;
    },
  },
};
</script>

<style>
.navbar-toggler-icon {
  background-image: url("data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 30 30'><path stroke='rgba(255, 255, 255, 1)' stroke-linecap='round' stroke-miterlimit='10' stroke-width='2' d='M4 7h22M4 15h22M4 23h22'/></svg>") !important;
}
:root {
  --bvt-primary-color: #bc02d1;
  --bvt-bg-secondary: #ddd;
  --bvt-timeline-color: #aaa;
  --bvt-timeline-text-color: #000000;
  --bvt-border-color: var(--bvt-timeline-color);
  --bvt-duration-color: var(--bvt-primary-color);
  --bvt-box-shadow1: 0 1px 6px rgba(0, 0, 0, 0.12),
    0 1px 4px rgba(0, 0, 0, 0.24);
}
.timeline-date {
  color: transparent;
}
.body {
  background-color: #000000;
}

.center-img {
  display: block;
  margin-left: auto;
  margin-right: auto;
  width: 50%;
}

.blog-img {
  position: relative;
}

.blog-img > a {
  position: absolute;
  background: white;
  bottom: 0;
  left: 0;
}
</style>
