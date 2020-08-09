<template>
  <b-container class="page animate__animated animate__fadeIn">
    <b-row>
      <b-col md="3"></b-col>
      <b-col>
        <h2>Get in touch 💌</h2>
        <p class="text-left">
          If you have any question or just want to say hi, i'll try my best to
          get back to you.
        </p>
        <b-form @submit="onSubmit">
          <b-alert show variant="success" v-if="showAlert">
            <strong>All done 🎉</strong><br />
            Thanks for reaching out {{ this.form.name }}, I'll reply as soon as
            i can.
          </b-alert>
          <b-form-group id="input-group-1" label="Your Name:" label-for="name">
            <b-form-input
              id="name"
              v-model="form.name"
              required
              placeholder="John Doe"
            ></b-form-input>
          </b-form-group>
          <b-form-group
            id="input-group-2"
            label="Your Email:"
            label-for="email"
          >
            <b-form-input
              id="email"
              v-model="form.email"
              type="email"
              required
              placeholder="john@doe.com"
            ></b-form-input>
          </b-form-group>
          <b-form-group
            id="input-group-3"
            label="Your Message"
            label-for="message"
          >
            <b-form-textarea
              id="message"
              v-model="form.message"
              no-resize
              rows="3"
              required
              placeholder="Watsup Elijah, are you available for.."
            ></b-form-textarea>
          </b-form-group>
          <b-button type="submit" variant="primary">Submit</b-button>
          <br /><br />
        </b-form>
      </b-col>
      <b-col md="3"></b-col>
    </b-row>
  </b-container>
</template>
<script>
export default {
  data() {
    return {
      showAlert: false,
      form: {
        name: "",
        email: "",
        message: ""
      }
    };
  },
  methods: {
    onSubmit: function(e) {
      e.preventDefault();
      var name = this.form.name;
      var email = this.form.email;
      var message = this.form.message;
      fetch(`formspree/url/send?name=${name}&email=${email}&message=${message}`)
        .then(res => res.json())
        .then(() => {
          this.showAlert = true;
        })
        .catch(() => {
          alert("Sending message failed, please try again");
        });
    }
  },
  head: {
    title: "Contact 📧 - Asaolu Elijah",
    meta: [
      {
        hid: "description",
        name: "description",
        content: "Do you have any enquires? Send a message now to Asaolu Elijah"
      },
      {
        hid: "og:title",
        name: "og:title",
        content: "Contact 📧 - Asaolu Elijah"
      },
      {
        property: "og:description",
        content: "Do you have any enquires? Send a message now to Asaolu Elijah"
      },
      {
        hid: "og:image",
        name: "og:image",
        content: require("@/assets/contact.jpg")
      }
    ]
  }
};
</script>
<style scoped>
.container {
  margin-top: 120px;
}
form {
  margin-top: 40px;
  text-align: left;
}
</style>
