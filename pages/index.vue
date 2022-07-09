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
        margin-bottom: 50px;
        margin-top: 18px;
        overflow: hidden;
        position: relative;
      "
    >
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

    <div style="background-color: gray; border-radius: 42px">
      <b-row class="pb-5 p-3" align-v="center">
        <b-col cols="12" md="6" sm="12">
          <div class="p-2">
            <b-img
              style="border-radius: 300px; max-height: 418px; width: 590px"
              src="/images/pool.jpg"
              fluid
              alt="Responsive image"
            ></b-img>
          </div>
        </b-col>
        <b-col cols="12" md="6" sm="12">
          <h1
            class="pb-3"
            style="font-weight: 800; font-size: 30px; color: #43ee9c"
          >
            A METAVERSE MADE FOR THE ARTIST, BY ARTISTS.
          </h1>
          <h2 class="text-white" style="font-weight: 800; font-size: 30px">
            BE THE FIRST TO KNOW
          </h2>
          <h2 class="text-white pb-3" style="font-weight: 800; font-size: 30px">
            SIGN UP NOW
          </h2>
          <h4 class="text-white pb-3">134 days, 09 hours 32 minutes</h4>
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
              <h1 style="font-weight: 800; color: rgba(67, 238, 156, 1)">
                IT’S YOUR WORLD
              </h1>
              <h1 style="font-weight: 800; color: rgba(67, 238, 156, 1)">
                AND ITS YOUR STAGE
              </h1>

              <p>
                Welcome to the MTRXVerse, the ultimate talent and performance
                Metaverse built by actual music industry artists to help
                creators share their world with the world; no matter the
                location. From fully customizable performance stages, to fashion
                airdrops, to brand sponsored immersive activations, to full on
                music festivals with custom effects the MTRXVERSE is the
                ultimate home for the next generation of artists to directly
                connect with their fans around the globe in a whole new way.
                 You no longer have to BE THERE to BE THERE. Enter the MTRXVerse
              </p>
              <b-button
                pill
                class="border-0"
                style="background-color: #00c0f9; border-color: #00c0f9"
                >LEARN MORE</b-button
              >
            </b-col>

            <b-col class="ml-auto py-3" cols="12" md="4" sm="12">
              <b-img
                src="/images/banner-logo.png"
                style="max-width: 300px"
                fluid
                alt="Fluid image"
              ></b-img>
            </b-col>
          </b-row>
        </b-card>
      </div>

      <div class="pb-5 text-white">
        <h1
          class="text-center"
          style="font-weight: 700; font-size: 36px; color: #43ee9c"
        >
          ROADMAP
        </h1>

        <b-img
          class="center-img"
          style="width: 75%; padding-left: 1rem"
          src="/images/timeline.png"
          fluid
          alt="Responsive image"
        ></b-img>
      </div>
      <div class="pb-5">
        <b-img fluid src="/images/metamansion.png" class="center-img"></b-img>

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

      <div>
        <h1 class="text-center text-white pb-5" style="font-weight: 700">
          NEWS
        </h1>
        <b-card-group deck>
          <b-card
            v-for="item in news"
            :key="item.id"
            img-src="https://picsum.photos/300/300/?image=41"
            img-alt="Image"
            img-top
            style="background-color: #07fcfc !important"
          >
            <b-card-title>
              {{ item.title }}
            </b-card-title>
            <b-card-text>
              {{ item.content }}
            </b-card-text>
            <template #footer>
              <small class="text-muted">Last updated 3 mins ago</small>
            </template>
          </b-card>
        </b-card-group>
      </div>
    </div>

    <div class="pb-5 mt-5">
      <b-card
        no-body
        class="text-white align-items-center"
        style="border-radius: 25px; background-color: gray"
      >
        <h1
          class="text-center text-white"
          style="font-weight: 700; font-size: 64px"
        >
          Powered By Klaytn
        </h1>
        <b-row align-v="center" align-h="center" class="py-4 w-100">
          <b-col class="ml-md-auto" cols="12" md="6" sm="12">
            <p style="font-weight: 700; font-size: 22px">
              Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
              eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut
              enim ad minim veniam, quis nostrud exercitation ullamco laboris
              nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in
              reprehenderit in voluptate velit esse cillum dolore
            </p>
          </b-col>

          <b-col class="ml-auto" cols="12" md="4" sm="12">
            <b-img
              src="/images/klaytn.png"
              style="max-width: 300px"
              fluid
              alt="Fluid image"
            ></b-img>
          </b-col>
        </b-row>
      </b-card>
    </div>

    <div class="d-none d-md-flex justify-content-center">
      <b-btn variant="link">
        <b-img src="/images/social/youtube.svg"></b-img>
      </b-btn>
      <b-btn variant="link">
        <b-img src="/images/social/facebook.svg"></b-img>
      </b-btn>
      <b-btn variant="link">
        <b-img src="/images/social/twitter.svg"></b-img>
      </b-btn>
      <b-btn variant="link">
        <b-img src="/images/social/twitch.svg"></b-img>
      </b-btn>
      <b-btn variant="link">
        <b-img src="/images/social/instagram.svg"></b-img>
      </b-btn>
      <b-btn variant="link">
        <b-img src="/images/social/discord.svg"></b-img>
      </b-btn>
    </div>
  </b-container>
</template>

<script>
import VueTimeline from "bs-vue-timeline";
export default {
  name: "IndexPage",
  layout: "main",
  components: {
    VueTimeline,
  },
  data() {
    return {
      play_video: false,
      timelineItems: [
        {
          title: "Milestone 1",
          subtitle: "System Engineer",
          content:
            "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.",
        },
        {
          title: "Milestone 2",
          subtitle: "Programmer",
          content:
            "Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.",
        },
        {
          title: "Milestone 3",
          subtitle: "Internship / Volunteer",
          content:
            "Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.",
        },
      ],
      form: {
        email: "",
      },
      news: [
        {
          id: 1,
          title: "title",
          subtitle: "subtitle",
          content: "blah",
        },
        {
          id: 2,
          title: "title",
          subtitle: "subtitle",
          content: "blah",
        },
        {
          id: 3,
          title: "title",
          subtitle: "subtitle",
          content: "blah",
        },
      ],
      slide: 0,
      sliding: null,
    };
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
</style>
