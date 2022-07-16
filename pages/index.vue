<template>
  <b-container>
    <b-navbar toggleable="lg" type="dark" style="background-color: #000000">
      <b-navbar-brand href="#">
        <MtrxLogo style="height: 60px" />
      </b-navbar-brand>

      <b-navbar-toggle
        style="border-color: transparent; color: white"
        class="text-white"
        target="nav-collapse"
      ></b-navbar-toggle>

      <b-collapse id="nav-collapse" is-nav>
        <b-navbar-nav>
          <!-- <b-nav-item active style="font-weight: 600" href="#">
            Tech
          </b-nav-item>
          <b-nav-item active style="font-weight: 600" href="#">
            Metaverse
          </b-nav-item>
          <b-nav-item active style="font-weight: 600" href="#">
            News
          </b-nav-item> -->
        </b-navbar-nav>
        <b-navbar-nav class="d-none d-md-flex ml-auto">
          <a class="px-2" href="//instagram.com/mtrx_verse" target="_blank">
            <b-img-lazy src="/images/social/instagram.svg"></b-img-lazy>
          </a>

          <a
            class="px-2"
            href="//youtube.com/channel/UCsBrwjLD7ZeOK2AcZoXN7Bw"
            target="_blank"
          >
            <b-img-lazy src="/images/social/youtube.svg" fluid></b-img-lazy>
          </a>

          <a
            class="px-2"
            href="//facebook.com/Mtrxverse-100990529327655/"
            target="_blank"
          >
            <b-img-lazy src="/images/social/facebook.svg"></b-img-lazy>
          </a>

          <a class="px-2" href="//twitter.com/mtrxverse" target="_blank">
            <b-img-lazy src="/images/social/twitter.svg"></b-img-lazy>
          </a>

          <!-- <a class="px-2" href="//twitch.com/mtrxverse" target="_blank">
            <b-img-lazy src="/images/social/twitch.svg"></b-img-lazy>
          </a> -->

          <!-- <a class="px-2" href="//discord.gg/SJn7naaQ" target="_blank">
            <b-img-lazy src="/images/social/discord.svg"></b-img-lazy>
          </a> -->
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
          src="/images/mainimage.png"
          fluid
          style="position: relative; max-height: 592px; width: 100%"
        >
        </b-img-lazy>
        <b-button
          style="
            position: absolute;
            bottom: 50%;
            left: 48%;
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
          loop
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
      <div class="d-none d-md-block">
        <b-row class="pb-5 p-3" align-v="center">
          <b-col cols="12" md="6" sm="12">
            <div class="p-2">
              <b-img-lazy
                style="border-radius: 300px; max-height: 418px; width: 590px"
                src="/images/second-flamingo.png"
                fluid
                alt="Responsive image"
              ></b-img-lazy>
            </div>
          </b-col>
          <b-col class="pt-3" cols="12" md="6" sm="12">
            <h2
              class="pb-3"
              style="
                font-family: 'Lcd';
                font-style: normal;
                font-weight: 800;
                font-size: 30px;
                line-height: 30px;
                color: #43ee9c;
                text-shadow: 0 0 0.15em #0fa;
                filter: blur(0.007em);
              "
            >
              A METAVERSE MADE FOR THE ARTIST, BY ARTISTS.
            </h2>
            <h2
              class="text-white"
              style="
                font-style: normal;
                font-weight: 800;
                font-size: 30px;
                line-height: 30px;
              "
            >
              BE THE FIRST TO KNOW
            </h2>
            <h2
              class="text-white pb-3"
              style="
                font-style: normal;
                font-weight: 800;
                font-size: 30px;
                line-height: 30px;
              "
            >
              SIGN UP NOW
            </h2>

            <h4 class="text-white pb-3" id="timer"></h4>

            <mailchimp-subscribe
              url="https://mtrxverse.us9.list-manage.com/subscribe/post-json"
              user-id="e21337cbe4c69f86f9ca3f6f2"
              list-id="94ed62df3d"
              @error="onError"
              @success="onSuccess"
            >
              <template
                v-slot="{ subscribe, setEmail, error, success, loading }"
              >
                <b-form inline @reset="onReset" @submit.prevent="subscribe">
                  <b-form-input
                    style="
                      background-color: transparent;
                      border-color: #6e0095;
                      font-family: 'Lcd';
                      font-style: italic;
                      font-weight: 300;
                      font-size: 24px;
                      line-height: 33px;
                    "
                    id="input-1"
                    v-model="form.email"
                    @input="setEmail"
                    :state="emailState"
                    type="email"
                    placeholder="EMAIL"
                    required
                  ></b-form-input>

                  <div v-if="error" class="text-danger pt-1">
                    {{ error }}
                  </div>

                  <b-button
                    :disabled="!emailState"
                    type="submit"
                    class="d-none d-md-block mt-3"
                    style="
                      background-color: #00c0f9;
                      border-color: #00c0f9;
                      font-family: 'Inter';
                      font-style: italic;
                      font-weight: 300;
                      font-size: 20px;
                      line-height: 33px;
                    "
                    >ENTER THE MTRX
                  </b-button>
                </b-form>
              </template>
            </mailchimp-subscribe>
          </b-col>
        </b-row>
      </div>

      <b-row
        class="d-block d-md-none pb-3 p-0 m-0 text-center"
        align-v="center"
      >
        <b-col class="pt-3" cols="12" md="6" sm="12">
          <h2
            class="py-3"
            style="
              font-family: 'Lcd';
              font-style: normal;
              font-weight: 800;
              font-size: 20px;
              line-height: 30px;
              color: #43ee9c;
              text-shadow: 0 0 0.15em #0fa;
              filter: blur(0.007em);
            "
          >
            A METAVERSE MADE FOR THE ARTIST, BY ARTISTS.
          </h2>
          <h2
            class="text-white"
            style="
              font-style: normal;
              font-weight: 800;
              font-size: 20px;
              line-height: 30px;
              text-shadow: 0 0 0.15em #0fa;
              filter: blur(0.007em);
            "
          >
            BE THE FIRST TO KNOW
          </h2>
          <h2
            class="text-white pb-2"
            style="
              font-style: normal;
              font-weight: 800;
              font-size: 20px;
              line-height: 30px;
            "
          >
            SIGN UP NOW
          </h2>

          <h4
            class="text-white pb-3"
            style="font-family: 'Inter'"
            id="timer2"
          ></h4>

          <mailchimp-subscribe
            url="https://mtrxverse.us9.list-manage.com/subscribe/post-json"
            user-id="e21337cbe4c69f86f9ca3f6f2"
            list-id="94ed62df3d"
            @error="onError"
            @success="onSuccess"
          >
            <template v-slot="{ subscribe, setEmail, error, success, loading }">
              <b-form inline @reset="onReset" @submit.prevent="subscribe">
                <b-form-input
                  style="
                    background-color: transparent;
                    border-color: #6e0095;
                    font-family: 'Lcd';
                    line-height: 33px;
                    font-size: 22px;
                  "
                  :class="emailState ? 'text-white' : 'text-gray'"
                  id="input-1"
                  v-model="form.email"
                  @input="setEmail"
                  :state="emailState"
                  type="email"
                  placeholder="EMAIL"
                  required
                ></b-form-input>

                <div v-if="error" class="text-danger pt-1">
                  {{ error }}
                </div>

                <b-button
                  :disabled="!emailState"
                  block
                  class="my-3"
                  type="submit"
                  style="
                    background-color: #00c0f9;
                    border-color: #00c0f9;
                    font-family: 'Open Sans';
                    font-style: italic;
                    font-weight: 300;
                    font-size: 22px;
                    line-height: 33px;
                  "
                  >ENTER THE MTRX
                </b-button>
              </b-form>
            </template>
          </mailchimp-subscribe>
        </b-col>
        <b-col cols="12" md="6" sm="12">
          <div class="p-2">
            <b-img-lazy
              style="border-radius: 300px; max-height: 418px; width: 590px"
              src="/images/second-flamingo.png"
              fluid
              alt="Responsive image"
            ></b-img-lazy>
          </div>
        </b-col>
      </b-row>

      <div class="pb-5">
        <b-card
          no-body
          class="d-none d-md-block text-white align-items-center p-3"
          style="border-radius: 100px; background: rgba(94, 94, 94, 0.5)"
        >
          <b-row align-v="center" align-h="center" class="py-4 w-100">
            <b-col class="ml-md-auto" cols="12" md="6" sm="12">
              <h2
                style="
                  font-family: 'Lcd';
                  font-style: normal;
                  font-weight: 800;
                  font-size: 40px;
                  color: rgba(67, 238, 156, 1);
                  margin: 0px;
                  text-shadow: 0 0 0.15em #0fa;
                  filter: blur(0.007em);
                "
              >
                IT’S YOUR WORLD
              </h2>
              <h2
                style="
                  font-family: 'Lcd';
                  font-style: normal;
                  font-weight: 800;
                  font-size: 40px;
                  color: rgba(67, 238, 156, 1);
                  margin: 0px;
                  text-shadow: 0 0 0.15em #0fa;
                  filter: blur(0.007em);
                "
                class="pb-3"
              >
                AND ITS YOUR STAGE
              </h2>
              <p
                style="
                  font-family: 'Inter';
                  font-style: normal;
                  font-weight: 800;
                  font-size: 15px;
                  line-height: 30px;
                "
                class="pb-2"
              >
                Welcome to the MTRXVerse, the ultimate live entertainment
                metaverse built by actual industry professionals to help
                creators share THEIR world, with THE world; no matter the
                location. From fully customizable performances stages, to
                fashion airdrops, to brand sponsored immersive activations, to
                full on music festivals with custom effects: The MTRXVerse is
                the ultimate home for the next generation of creators to
                directly connect with their fans around the globe in a whole new
                way.
              </p>
              <p
                style="
                  font-family: 'Inter';
                  font-style: normal;
                  font-weight: 800;
                  font-size: 15px;
                  line-height: 30px;
                "
                class="pb-2"
              >
                You no longer have to “Be there” to “Be there”
              </p>
              <p
                style="
                  font-family: 'Inter';
                  font-style: normal;
                  font-weight: 800;
                  font-size: 15px;
                  line-height: 30px;
                "
                class="pb-2"
              >
                Enter the MTRXVerse
              </p>
            </b-col>

            <b-col class="ml-auto py-3" cols="12" md="4" sm="12">
              <MLogo style="width: 230px" />
              <!-- <b-img-lazy
                src="/images/banner-logo.svg"
                fluid
                alt="Fluid image"
              ></b-img-lazy> -->
            </b-col>
          </b-row>
        </b-card>
        <b-card
          no-body
          class="d-block d-md-none text-white align-items-center"
          style="border-radius: 100px; background: transparent"
        >
          <b-row
            align-v="center"
            align-h="center"
            class="w-100 text-center p-0 m-0"
          >
            <b-col class="ml-md-auto" cols="12" md="6" sm="12">
              <h2
                style="
                  font-family: 'Lcd';
                  font-style: normal;
                  font-weight: 800;
                  font-size: 20px;
                  color: rgba(67, 238, 156, 1);
                  margin: 0px;
                  text-shadow: 0 0 0.15em #0fa;
                  filter: blur(0.007em);
                "
              >
                IT’S YOUR WORLD
              </h2>
              <h2
                style="
                  font-family: 'Lcd';
                  font-style: normal;
                  font-weight: 800;
                  font-size: 20px;

                  color: rgba(67, 238, 156, 1);
                  margin: 0px;
                  text-shadow: 0 0 0.15em #0fa;
                  filter: blur(0.007em);
                "
                class="pb-3"
              >
                AND ITS YOUR STAGE
              </h2>

              <p
                style="
                  font-family: 'Inter';
                  font-style: normal;
                  font-weight: 800;
                  font-size: 15px;
                  line-height: 30px;
                "
                class="pb-2"
              >
                Welcome to the MTRXVerse, the ultimate live entertainment
                metaverse built by actual industry professionals to help
                creators share THEIR world, with THE world; no matter the
                location. From fully customizable performances stages, to
                fashion airdrops, to brand sponsored immersive activations, to
                full on music festivals with custom effects: The MTRXVerse is
                the ultimate home for the next generation of creators to
                directly connect with their fans around the globe in a whole new
                way.
              </p>
              <p
                style="
                  font-family: 'Inter';
                  font-style: normal;
                  font-weight: 800;
                  font-size: 15px;
                  line-height: 30px;
                "
                class="pb-2"
              >
                You no longer have to “Be there” to “Be there”
              </p>
              <p
                style="
                  font-family: 'Inter';
                  font-style: normal;
                  font-weight: 800;
                  font-size: 15px;
                  line-height: 30px;
                "
                class="pb-2"
              >
                Enter the MTRXVerse
              </p>
            </b-col>
          </b-row>
        </b-card>
      </div>

      <div class="pb-5 text-white">
        <b-img-lazy
          fluid
          class="pb-2 center-img"
          style="max-width: 250px"
          src="/images/metafest.svg"
        ></b-img-lazy>

        <h1
          class="d-none d-md-block text-center"
          style="
            font-family: 'Lcd';
            font-style: normal;
            font-weight: 800;
            font-size: 40px;
            color: #43ee9c;
            letter-spacing: 0.25em;
            text-shadow: 0 0 0.15em #0fa;
            filter: blur(0.007em);
          "
        >
          ROADMAP
        </h1>

        <h1
          class="d-block d-md-none text-center"
          style="
            font-family: 'Lcd';
            font-style: normal;
            font-weight: 800;
            font-size: 20px;
            color: #43ee9c;
            letter-spacing: 0.25em;
            text-shadow: 0 0 0.15em #0fa;
            filter: blur(0.007em);
          "
        >
          ROADMAP
        </h1>

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
    </div>

    <div class="py-3">
      <b-img-lazy
        fluid
        src="/images/metamansion.png"
        class="d-none d-md-block center-img"
      ></b-img-lazy>

      <b-img-lazy
        fluid
        src="/images/metamansion.png"
        class="d-block d-md-none center-img w-100"
      ></b-img-lazy>

      <b-carousel
        id="carousel-1"
        class="m-0 p-0 py-3"
        v-model="slide"
        :interval="4000"
        controls
        indicators
        @sliding-start="onSlideStart"
        @sliding-end="onSlideEnd"
      >
        <b-carousel-slide
          v-for="slide in carousell_slides"
          :key="slide.id"
          :img-src="slide.link"
        >
        </b-carousel-slide>
      </b-carousel>

      <h2
        class="text-center text-white py-4"
        style="
          font-family: 'Montserrat';
          font-style: normal;
          font-weight: 700;
          font-size: 48px;
          line-height: 72px;
        "
      >
        NEWS
      </h2>
      <b-card-group class="p-3" deck>
        <b-card
          v-for="item in news"
          :key="item.id"
          style="background-color: #07fcfc !important"
          no-body
        >
          <div class="p-2">
            <b-card-img class="blog-img" :src="item.image" alt="Image">
            </b-card-img>
            <a
              :href="item.link"
              target="_blank"
              style="
                position: absolute;
                z-index: 10000;
                right: 2rem;
                top: 1rem;
                color: #07fcfc;
              "
              ><b-icon scale="2" icon="arrow-right"></b-icon
            ></a>

            <b-card-title
              class="pt-2"
              style="
                font-family: 'Lcd';
                font-style: normal;
                font-weight: 400;
                font-size: 26px;
                height: 96px;
                overflow: hidden;
                text-overflow: ellipsis;
                display: -webkit-box;
                -webkit-line-clamp: 3;
                line-clamp: 3;
                -webkit-box-orient: vertical;
              "
            >
              {{ item.title }}
            </b-card-title>
            <b-card-text
              style="
                height: 96px;
                font-family: 'Inter';
                font-style: normal;
                overflow: hidden;
                text-overflow: ellipsis;
                display: -webkit-box;
                -webkit-line-clamp: 4;
                line-clamp: 4;
                -webkit-box-orient: vertical;
              "
            >
              {{ item.content }}
            </b-card-text>
            <b-button
              :href="item.link"
              target="_blank"
              variant="light"
              style="font-family: 'Inter'; font-style: normal; font-weight: 400"
              >Read more</b-button
            >
          </div>
        </b-card>
      </b-card-group>
    </div>

    <div
      class="py-3"
      style="
        border-radius: 42px;
        background-image: url('/images/news.png'); /* The image used */
        height: 100%; /* You must set a specified height */
        background-position: center; /* Center the image */
        background-repeat: no-repeat; /* Do not repeat the image */
        background-size: cover; /* Resize the background image to cover the entire container */
      "
    >
      <div class="d-none d-md-block pb-5 mt-5" style="position: relative">
        <b-card
          no-body
          class="text-white align-items-center"
          style="background-color: transparent"
        >
          <div class="p-4">
            <h2
              class="text-center text-white"
              style="
                font-family: 'Inter';
                font-style: normal;
                font-weight: 700;
                font-size: 54px;
                margin: 0px;
              "
            >
              POWERED BY
            </h2>

            <h2
              class="text-center text-white"
              style="
                font-family: 'Inter';
                font-style: normal;
                font-weight: 700;
                font-size: 54px;
                margin: 0px;
              "
            >
              KLAYTN
            </h2>

            <b-row align-v="center" align-h="center" class="py-4 w-100">
              <b-col class="ml-md-auto" cols="12" md="6" sm="12">
                <p
                  style="
                    font-family: 'Inter';
                    font-style: normal;
                    font-weight: 700;
                    font-size: 15px;
                    line-height: 30px;
                  "
                >
                  Klaytn is a public blockchain focused on the metaverse,
                  gamefi, and the creator economy. Developed by internet giant
                  Kakao Corp, Klaytn is the dominant blockchain platform in
                  South Korea and is undergoing global growth from its
                  international base in Singapore.
                </p>
                <p
                  style="
                    font-family: 'Inter';
                    font-style: normal;
                    font-weight: 700;
                    font-size: 15px;
                    line-height: 30px;
                  "
                >
                  To empower all who wish to build, work, or play in the
                  metaverse, the Klaytn Foundation provides support to
                  developers, entrepreneurs, and content creators via the Klaytn
                  Growth Fund.
                </p>
                <p
                  style="
                    font-family: 'Inter';
                    font-style: normal;
                    font-weight: 700;
                    font-size: 15px;
                    line-height: 30px;
                  "
                >
                  Dive into the world of Klaytn, and let's play
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
        <!-- <b-img
          src="/images/m.png"
          fluid
          style="
            position: absolute;
            margin-left: auto;
            margin-right: auto;
            top: 2rem;
            left: 0;
            right: 0;
            text-align: center;
          "
        ></b-img> -->
      </div>
      <div class="d-block d-md-none py-3">
        <b-card
          no-body
          class="text-white align-items-center"
          style="background-color: transparent"
        >
          <div class="p-4">
            <h1
              class="text-center text-white"
              style="
                font-family: 'Inter';
                font-style: normal;
                font-weight: 700;
                font-size: 36px;
                font-weight: 700;
                margin: 0px;
              "
            >
              POWERED BY
            </h1>

            <h1
              class="text-center text-white"
              style="
                font-family: 'Inter';
                font-style: normal;
                font-weight: 700;
                font-size: 36px;
                font-weight: 700;
                margin: 0px;
              "
            >
              KLAYTN
            </h1>

            <b-row
              align-v="center"
              align-h="center"
              class="text-center py-4 w-100 p-0 m-0"
            >
              <b-col class="ml-auto pb-3" cols="12" md="4" sm="12">
                <b-img-lazy
                  src="/images/klaytn.png"
                  style="max-width: 300px"
                  fluid
                  alt="Fluid image"
                ></b-img-lazy>
              </b-col>
              <b-col class="ml-md-auto" cols="12" md="6" sm="12">
                <p
                  style="
                    font-family: 'Inter';
                    font-style: normal;
                    font-weight: 700;
                    font-size: 15px;
                    line-height: 30px;
                  "
                >
                  Klaytn is a public blockchain focused on the metaverse,
                  gamefi, and the creator economy. Developed by internet giant
                  Kakao Corp, Klaytn is the dominant blockchain platform in
                  South Korea and is undergoing global growth from its
                  international base in Singapore.
                </p>
                <p
                  style="
                    font-family: 'Inter';
                    font-style: normal;
                    font-weight: 700;
                    font-size: 15px;
                    line-height: 30px;
                  "
                >
                  To empower all who wish to build, work, or play in the
                  metaverse, the Klaytn Foundation provides support to
                  developers, entrepreneurs, and content creators via the Klaytn
                  Growth Fund.
                </p>
                <p
                  style="
                    font-family: 'Inter';
                    font-style: normal;
                    font-weight: 700;
                    font-size: 15px;
                    line-height: 30px;
                  "
                >
                  Dive into the world of Klaytn, and let's play
                </p>
              </b-col>
            </b-row>
          </div>
        </b-card>
      </div>
    </div>

    <b-container class="py-5">
      <b-row align-v="center">
        <b-col col md="5" sm="12">
          <div class="d-flex" style="width: 285px">
            <div>
              <MtrxLogo style="height: 120px" />
              <p
                class="text-white pb-3"
                style="
                  font-family: 'Inter';
                  font-style: normal;
                  font-weight: 700;
                  font-size: 22px;
                "
              >
                The Bridge Between Metaverse and IRL Events.
              </p>
            </div>

            <!-- <div>
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
            </div> -->
          </div>
        </b-col>
        <b-col col md="7" sm="12">
          <h2
            class="d-none d-md-block text-white text-center pb-3"
            style="font-weight: 700; text-decoration: underline"
          >
            JOIN THE WAITLIST
          </h2>
          <h2
            class="d-block d-md-none text-white pb-3"
            style="
              font-weight: 700;
              font-size: 20px;
              text-decoration: underline;
            "
          >
            JOIN THE WAITLIST
          </h2>

          <mailchimp-subscribe
            url="https://mtrxverse.us9.list-manage.com/subscribe/post-json"
            user-id="e21337cbe4c69f86f9ca3f6f2"
            list-id="94ed62df3d"
            @error="onError"
            @success="onSuccess"
          >
            <template v-slot="{ subscribe, setEmail, error, success, loading }">
              <b-form
                @submit.prevent="subscribe"
                style="justify-content: center"
                inline
                @reset="onReset"
              >
                <b-form-input
                  style="
                    background-color: transparent;
                    border-color: #6e0095;
                    font-family: 'Lcd';
                    font-style: italic;
                    font-weight: 300;
                    font-size: 24px;
                    line-height: 33px;
                  "
                  id="input-1"
                  v-model="form.email"
                  @input="setEmail"
                  :state="emailState"
                  type="email"
                  placeholder="EMAIL"
                  required
                ></b-form-input>

                <div v-if="error" class="text-danger pt-1">
                  {{ error }}
                </div>

                <b-button
                  :disabled="!emailState"
                  class="d-none d-md-block ml-3"
                  type="submit"
                  style="
                    background-color: #00c0f9;
                    border-color: #00c0f9;
                    font-family: 'Inter';
                    font-style: italic;
                    font-weight: 300;
                    font-size: 20px;
                    line-height: 33px;
                  "
                  >ENTER THE MTRX
                </b-button>

                <b-button
                  :disabled="!emailState"
                  block
                  type="submit"
                  class="d-block d-md-none mt-3"
                  style="
                    background-color: #00c0f9;
                    border-color: #00c0f9;
                    font-family: 'Inter';
                    font-style: italic;
                  "
                  >Enter the MTRX
                </b-button>
              </b-form>
            </template>
          </mailchimp-subscribe>
        </b-col>
      </b-row>
    </b-container>

    <div class="d-flex justify-content-center pb-4">
      <a class="px-2" href="//instagram.com/mtrx_verse" target="_blank">
        <b-img-lazy src="/images/social/instagram.svg"></b-img-lazy>
      </a>

      <a
        class="px-2"
        href="//youtube.com/channel/UCsBrwjLD7ZeOK2AcZoXN7Bw"
        target="_blank"
      >
        <b-img-lazy src="/images/social/youtube.svg" fluid></b-img-lazy>
      </a>

      <a
        class="px-2"
        href="//facebook.com/Mtrxverse-100990529327655/"
        target="_blank"
      >
        <b-img-lazy src="/images/social/facebook.svg"></b-img-lazy>
      </a>

      <a class="px-2" href="//twitter.com/mtrxverse" target="_blank">
        <b-img-lazy src="/images/social/twitter.svg"></b-img-lazy>
      </a>

      <!-- <a class="px-2" href="//twitch.com/mtrxverse" target="_blank">
        <b-img-lazy src="/images/social/twitch.svg"></b-img-lazy>
      </a> -->

      <!-- <a class="px-2" href="//discord.gg/SJn7naaQ" target="_blank">
        <b-img-lazy src="/images/social/discord.svg"></b-img-lazy>
      </a> -->
    </div>
    <div class="pb-3">
      <p
        class="m-0 p-0 text-center"
        style="
          font-family: 'Inter';
          font-style: normal;
          font-weight: 600;
          font-size: 14px;
          color: #e0e0e0;
        "
      >
        2022 MTRX Inc. All rights reserved
      </p>
    </div>
    <toast
      id="toast-email-saved"
      title="Registered successfully"
      body="Your email has been successfully registered."
      variant="success"
      icon="check-circle-fill"
    ></toast>
  </b-container>
</template>

<script>
import MtrxLogo from "../components/MtrxLogo.vue";
import MailchimpSubscribe from "vue-mailchimp-subscribe";
import Toast from "~/components/Toast";
import MLogo from "../components/MLogo.vue";
export default {
  name: "IndexPage",
  layout: "main",
  components: { MtrxLogo, MailchimpSubscribe, Toast, MLogo },
  data() {
    return {
      play_video: false,
      form: {
        email: "",
      },
      carousell_slides: [
        {
          id: 1,
          link: "/images/carousell1.png",
        },
        {
          id: 2,
          link: "/images/carousell2.png",
        },
        {
          id: 3,
          link: "/images/carousell3.png",
        },
        {
          id: 4,
          link: "/images/carousell4.png",
        },
        {
          id: 5,
          link: "/images/carousell5.png",
        },
      ],
      news: [
        {
          id: 1,
          title: "AP Photos Diplo Hamptons Party",
          subtitle: "subtitle",
          image: "/images/blog1.png",
          link: "https://www.apimages.com/search?query=David+Warren+&entitysearch=&st=ps&eventid=13480049&orderBy=Newest&title=NY:+MTRX+and+Anna+Rothschild+present+Diplo+at+a+VIP+party+at+the+MTRX+Metamansion+in+Sag+Harbor,+NY+on+July+4th,+2022&allfilters=&currItem=6f7fedac579948a3bb70a7736c10a273&toItem=24&fbclid=IwAR3D_sRrK2OBFbaye7l0sUxseeLVkVm9ZEH48h-tsiuF6WJw0_50nBYchpE",
          content:
            "Enjoy all the photos by AP images of our latest metamansion takeover. ",
        },
        {
          id: 2,
          title: "Parties take over the Hamptons for Fourth of July weekend",
          subtitle: "subtitle",
          image: "/images/blog2.png",
          link: "https://pagesix.com/2022/07/04/diplo-kaia-gerber-and-more-celebs-party-in-the-hamptons-for-fourth-of-july/?utm_campaign=iphone_nyp&utm_source=message_app",
          content:
            "Over the Fourth of July holiday weekend, hospitality guru Richie Akiva and Ronnie Madra threw a bash at Kissaki in Water Mill.",
        },
        {
          id: 3,
          title: "Enter MTRX: You Don’t Have To Be There, To Be There",
          subtitle: "subtitle",
          image: "/images/article3.png",
          link: "https://edmmaniac.com/enter-mtrx/",
          content:
            "Imagine a world where access to your favorite live experiences were always available and you were no longer bound by physical or financial limitations? ",
        },
      ],
      slide: 0,
      sliding: null,
    };
  },
  mounted() {
    // Set the date we're counting down to
    var countDownDate = new Date("Dec 22, 2022 00:00:00").getTime();
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
      // Display the result in the element with id="demo"
      document.getElementById("timer2").innerHTML =
        days + "d " + hours + "h " + minutes + "m " + seconds + "s ";
      // If the count down is finished, write some text
      if (distance < 0) {
        clearInterval(x);
        document.getElementById("timer").innerHTML = "EXPIRED";
        document.getElementById("timer2").innerHTML = "EXPIRED";
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
    onError() {
      console.log("error");
    },
    onSuccess() {
      console.log("success");
      this.$root.$bvToast.show("toast-email-saved");
    },
    onEmailChange(event) {
      console.log(event);
    },
  },
};
</script>

<style>
@font-face {
  font-family: "Montserrat";
  font-style: normal;
  font-weight: 700;
  font-display: swap;
  src: url("~assets/fonts/Montserrat.ttf") format("truetype");
}

@font-face {
  font-family: "OpenSans";
  font-style: normal;
  font-weight: 700;
  font-display: swap;
  src: url("~assets/fonts/OpenSans.ttf") format("truetype");
}

@font-face {
  font-family: "Lcd";
  font-style: normal;
  font-weight: 700;
  font-display: swap;
  src: url("~assets/fonts/Lcd.ttf") format("truetype");
}

@font-face {
  font-family: "Inter";
  font-style: normal;
  font-weight: 700;
  font-display: swap;
  src: url("~assets/fonts/Inter.ttf") format("truetype");
}

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
