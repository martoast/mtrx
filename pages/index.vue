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
    <div>
      <!-- Image and text -->
      <b-navbar variant="white" type="light">
        <b-navbar-brand href="#">
          <img
            src="/images/logo.svg"
            class="d-inline-block align-top"
            alt="Kitten"
          />
        </b-navbar-brand>
      </b-navbar>
    </div>
  </div>
</template>

<script>
export default {
  name: "IndexPage",
};
</script>
<style scoped>
body {
  background-image: url("/images/background.png");
}
</style>
