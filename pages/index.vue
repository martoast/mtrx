<template>
  <div
    style="
      background-image: url('/images/background.png');
      background-position: center;
      background-repeat: no-repeat;
      background-size: cover;
      height: 100vh;
      overflow: auto;
    "
  >
    <b-navbar toggleable="lg" type="light" variant="white">
      <b-navbar-brand href="#">
        <img
          src="/images/logo.svg"
          class="d-inline-block align-top"
          alt="logo "
        />
      </b-navbar-brand>

      <b-navbar-toggle
        class="text-gray"
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

    <b-row
      v-if="!play_video"
      style="height: calc(100vh - 86px)"
      class="px-5"
      align-v="center"
      align-h="center"
    >
      <b-col>
        <b-card
          class="justify-content-center"
          no-body
          style="
            background-color: #ddd;
            border: none;
            color: black;
            margin: 4px 2px;
            border-radius: 16px;
            height: 50vh;
          "
        >
          <b-container fluid>
            <b-row align-h="center" align-v="center">
              <b-col class="text-center">
                <span style="font-weight: 800; font-size: 24px">MTRX Inc.</span>
                <h1
                  style="
                    font-family: 'Open Sans';
                    font-style: normal;
                    font-weight: 800;
                    font-size: 51px;
                    color: #5c5858;
                  "
                >
                  Welcome to Mtrxverse.
                </h1>
                <b-button
                  class="mt-3"
                  @click="onplayVideo"
                  pill
                  variant="primary"
                  size="lg"
                  ><b-icon icon="play-circle-fill" scale="3"> </b-icon
                ></b-button>
              </b-col>
            </b-row>
          </b-container>
        </b-card>
      </b-col>
    </b-row>
    <b-container class="text-center m-0 p-0" fluid v-else>
      <video style="height: calc(100vh - 86px)" width="100%" autoplay muted>
        <source src="/videos/mainvideo.mp4" type="video/mp4" />
        Your browser does not support the video tag.
      </video>
    </b-container>
  </div>
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
  methods: {
    onplayVideo() {
      this.play_video = true;
    },
  },
};
</script>
<style scoped>
video::-webkit-media-controls-fullscreen-button {
  display: none !important;
}
</style>
