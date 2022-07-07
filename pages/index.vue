<template>
  <b-container>
    <b-navbar toggleable="lg" type="dark" style="background-color: #000000">
      <b-navbar-brand href="#">
        <img
          src="/images/logo.png"
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

    <div style="background: rgba(161, 102, 233, 0.3); border-radius: 25px">
      <b-row class="pb-5" align-v="center">
        <b-col cols="12" md="6" sm="12">
          <div class="p-2">
            <b-img
              style="border-radius: 25px"
              src="https://picsum.photos/1024/400/?image=41"
              fluid
              alt="Responsive image"
            ></b-img>
          </div>
        </b-col>
        <b-col cols="12" md="6" sm="12">
          <h1
            class="text-center"
            style="font-weight: 700; font-size: 36px; color: #43ee9c"
          >
            Listen to the Metaverse
          </h1>
          <b-container style="background-color: #c4c4c4">
            <h3 class="text-white p-3">
              A METAVERSE MADE FOR THE ARTIST, BY ARTISTS.
            </h3>
          </b-container>
        </b-col>
      </b-row>
      <div class="pb-5">
        <b-card
          no-body
          class="text-white align-items-center"
          style="border-radius: 25px; background: rgba(94, 94, 94, 0.5)"
        >
          <b-row align-v="center" align-h="center" class="py-4 w-100">
            <b-col class="ml-md-auto" cols="12" md="6" sm="12">
              <h1 style="font-weight: 800; color: rgba(251, 119, 208, 1)">
                Powered By Klaytn
              </h1>
              <p>
                Klaytn-contracts` is an open source smart contract library which
                provides reusable building blocks for developers to easily use
                in their Klaytn based projects. It contains a full suite of
                standardized smart contract interfaces, libraries, and
                implementations for quick and safe inheritance and development.
                Below are a few items which are widely used and included in the
                klaytn-contracts:
              </p>
              <b-button
                pill
                class="border-0"
                style="
                  background: rgb(94, 162, 239);
                  background: linear-gradient(
                    0deg,
                    rgba(94, 162, 239, 1) 6.77%,
                    rgba(209, 45, 156, 0.8057598039215687) 100%
                  );
                "
                >Read More About Klaytn</b-button
              >
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

      <div class="pb-5 text-white">
        <h1
          class="text-center"
          style="font-weight: 700; font-size: 36px; color: #43ee9c"
        >
          ROADMAP TO METAWEEK
        </h1>
        <div class="text-center">
          <b-img
            src="/images/timeline.png"
            fluid
            alt="Responsive image"
          ></b-img>
        </div>
      </div>

      <!-- <client-only placeholder="loading...">
        <VueTimeline
          ref="timeline"
          :timeline-items="timelineItems"
          :individualClasses="true"
        />
      </client-only> -->
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
    };
  },
  methods: {
    onplayVideo() {
      this.play_video = true;
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
</style>
