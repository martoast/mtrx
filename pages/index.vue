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
    <b-navbar class="position-sticky" variant="white" type="light">
      <b-navbar-brand href="#">
        <img
          src="/images/logo.svg"
          class="d-inline-block align-top"
          alt="logo "
        />
      </b-navbar-brand>
      <b-navbar-nav>
        <b-nav-item active style="font-weight: 600" href="#">Tech</b-nav-item>
        <b-nav-item active style="font-weight: 600" href="#"
          >Metaverse</b-nav-item
        >
        <b-nav-item active style="font-weight: 600" href="#">News</b-nav-item>
      </b-navbar-nav>
    </b-navbar>
    <b-row
      style="height: calc(100vh - 86px)"
      class="px-5"
      align-v="center"
      align-h="center"
    >
      <b-col>
        <b-card
          v-if="!play"
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
              <b-col cols="12" md="6" sm="12" class="text-center">
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
                  Enter the Mtrxverse.
                </h1>
              </b-col>
              <b-col class="py-2" cols="12" md="6" sm="12">
                <b-embed
                  type="iframe"
                  aspect="16by9"
                  src="https://www.youtube.com/embed/zpOULjyy-n8?rel=0"
                  allowfullscreen
                ></b-embed>
              </b-col>
            </b-row>
          </b-container>
        </b-card>
        <b-embed
          v-else
          type="iframe"
          frameborder="0"
          src="https://www.youtube.com/embed/dQw4w9WgXcQ?autoplay=1"
          allow="autoplay"
          allowfullscreen
        ></b-embed>
      </b-col>
    </b-row>
  </div>
</template>

<script>
export default {
  name: "IndexPage",
  layout: "main",
  data() {
    return {
      play: false,
    };
  },
  methods: {
    onPlay() {
      this.play = true;
    },
  },
};
</script>
