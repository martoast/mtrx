<template>
  <b-container>
    <b-navbar toggleable="lg" type="dark" style="background-color: #000000">
      <b-navbar-brand href="#">
        <img
          src="/images/logo.svg"
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

    <div class="pb-3">
      <b-card
        no-body
        class="text-center bg-secondary text-white"
        style="border-radius: 25px"
      >
        <b-row align-v="center" align-h="center" class="py-4">
          <b-col cols="12" md="6" sm="12">
            <h1 style="font-weight: 800; font-size: 40px">Powered By Klaytn</h1>
            <p class="px-3">
              Klaytn-contracts` is an open source smart contract library which
              provides reusable building blocks for developers to easily use in
              their Klaytn based projects. It contains a full suite of
              standardized smart contract interfaces, libraries, and
              implementations for quick and safe inheritance and development.
              Below are a few items which are widely used and included in the
              klaytn-contracts:
            </p>
          </b-col>

          <b-col cols="12" md="6" sm="12">
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
  </b-container>
</template>

<script>
export default {
  name: "IndexPage",
  layout: "main",
  data() {
    return {
      play_video: false,
    };
  },
  mounted() {
    document.querySelector("body").style.backgroundColor = "#000000";
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
</style>
