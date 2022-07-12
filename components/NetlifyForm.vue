<template>
  <b-form
    inline
    name="contactus"
    @submit="onSubmit"
    method="post"
    netlify
    netlify-honeypot="bot-field"
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
      type="submit"
      :disabled="!emailState"
      class="d-none d-md-block ml-3"
      style="background-color: #00c0f9; border-color: #00c0f9"
      >ENTER THE MTRX
    </b-button>

    <b-button
      type="submit"
      class="d-block d-md-none mt-3"
      style="background-color: #00c0f9; border-color: #00c0f9"
      >Enter the MTRX
    </b-button>
  </b-form>
</template>

<script>
export default {
  data() {
    return {
      form: {
        email: "",
      },
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
    encode(data) {
      return Object.keys(data)
        .map(
          (key) => `${encodeURIComponent(key)}=${encodeURIComponent(data[key])}`
        )
        .join("&");
    },
    onSubmit(event) {
      event.preventDefault();
      alert(JSON.stringify(this.form));
      fetch("/", {
        method: "POST",
        headers: { "Content-Type": "application/x-www-form-urlencoded" },
        body: this.encode({ "form-name": "contact", ...this.form }),
      })
        .then(() => alert("Email sent."))
        .catch((error) => alert(error));
    },
  },
};
</script>
