<template>
  <div>
    <b-toast
      :id="id"
      variant="white"
      header-class="d-none"
      :toast-class="['border-' + variant, 'light-shadow-sm']"
      body-class="p-4"
      auto-hide-delay="5000"
      solid
      no-auto-hide
      no-fade
    >
      <template #default="{ hide }">
        <div class="d-flex justify-content-between">
          <b-media no-body>
            <b-media-aside class="mr-4" vertical-align="center">
              <b-icon :icon="icon" :variant="variant" font-scale="1.5"></b-icon>
            </b-media-aside>

            <b-media-body>
              <h6
                style="
                  font-family: 'Lcd';
                  font-style: italic;
                  font-weight: 300;
                  font-size: 22px;
                  line-height: 33px;
                "
                class="mb-1 text-deep-blue"
              >
                {{ title }}
              </h6>
              <small class="text-muted"> {{ body }}</small>
            </b-media-body>
          </b-media>
          <b-button
            variant="link"
            class="ml-4 my-auto p-0 d-flex align-items-center justify-content-center"
            @click="hide"
          >
            <b-icon icon="x" style="color: #00c0f9" font-scale="1.5"></b-icon>
          </b-button>
        </div>
      </template>
    </b-toast>
  </div>
</template>

<script>
export default {
  props: ["id", "title", "body", "variant", "icon"],
};
</script>
<style>
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
</style>
