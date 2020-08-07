<template>
  <b-row style="margin-left: 0;margin-right: 0;">
    <b-col md="4">
      <b-img
        :src="avatar"
        id="avatar-img"
        alt="Asaolu Elijah Memoji"
        @mouseenter="changeAvatar"
        @mouseleave="changeAvatar"
      />
    </b-col>
    <b-col md="8">
      <h2 class="intro animate__animated animate__fadeInUp animate__fast">
        Hi 👋,
        <br />I<span>'m Asaolu&nbsp;Elijah</span>.
      </h2>
      <div class="col-md-10 info">
        A <b>front-end developer</b> and <b>technical writer</b> passionate
        about solving problems with tech.<br />
        I am skilled with building exceptional <b>websites</b> and
        <b>mobile applications</b>, and currently i'm exploring the AI
        (Artificial Intelligence) ecosystem.
        <br />
        <b-button
          class="action-btn animate__animated animate__wobble animate__delay-4s animate__fast"
          to="/projects"
          >Explore ></b-button
        >
        <b-button class="action-btn" to="/contact" variant="primary"
          >Get In Touch</b-button
        >
        <div
          class="social-icons animate__animated animate__fadeInUp animate__delay-1s"
        >
          <a
            href="http://github.com/asaoluelijah"
            target="_blank"
            rel="noopener"
          >
            <GithubIcon />
          </a>
          <a
            href="https://ng.linkedin.com/in/asaolu-elijah-1070101b0"
            target="_blank"
            rel="noopener"
          >
            <LinkedinIcon />
          </a>
          <a
            href="https://twitter.com/asaolu_elijah"
            target="_blank"
            rel="noopener"
          >
            <TwitterIcon />
          </a>
          <a
            href="https://facebook.com/asaoluelijah01"
            target="_blank"
            rel="noopener"
          >
            <FacebookIcon />
          </a>
          <a
            href="mailto:info4a.elijah@gmail.com"
            target="_blank"
            rel="noopener"
          >
            <MailIcon />
          </a>
        </div>
      </div>
    </b-col>
  </b-row>
</template>

<script>
import GithubIcon from "vue-ionicons/dist/logo-github.vue";
import LinkedinIcon from "vue-ionicons/dist/logo-linkedin.vue";
import TwitterIcon from "vue-ionicons/dist/logo-twitter.vue";
import FacebookIcon from "vue-ionicons/dist/logo-facebook.vue";
import MailIcon from "vue-ionicons/dist/md-mail.vue";
export default {
  name: "Home",
  components: { GithubIcon, LinkedinIcon, TwitterIcon, FacebookIcon, MailIcon },
  data() {
    return {
      avatar: require("@/assets/avatar-1.webp")
    };
  },
  head: {
    title: "Portfolio ⚡ - Asaolu Elijah",
    meta: [
      {
        hid: "description",
        name: "description",
        content:
          "Asaolu Elijah is an awesome front-end developer and technical writer, passionate about building solutions that works across multiple platforms with high accessibility approach. Elijah has vast knowledge in web development with over 3+ years experience in building actual products"
      },
      {
        hid: "og:title",
        name: "og:title",
        content: "Portfolio ⚡ - Asaolu Elijah"
      },
      {
        property: "og:description",
        content:
          "Asaolu Elijah is an awesome front-end developer and technical writer, passionate about building solutions that works across multiple platforms with high accessibility approach. Elijah has vast knowledge in web development with over 3+ years experience in building actual products"
      },
      { hid: "og:image", name: "og:image", content: "~/assets/coding.png" }
    ]
  },
  methods: {
    changeAvatar() {
      if (this.avatar == require("@/assets/avatar-2.webp")) {
        this.avatar = require("@/assets/avatar-1.webp");
      } else {
        this.avatar = require("@/assets/avatar-2.webp");
      }
    }
  },
  mounted() {
    this.$nextTick(() => {
      this.$nuxt.$loading.start();

      setTimeout(() => this.$nuxt.$loading.finish(), 500);
    });
  }
};
</script>

<style scoped>
.row {
  margin-top: 170px;
}
.action-btn {
  display: inline-table;
  margin: 7px;
}
.info {
  margin-top: 10px;
  text-align: left;
  line-height: 2em;
  font-size: 18px;
  font-weight: normal;
  margin-left: 7px;
}
img {
  background-color: rgb(46, 42, 42);
  border-radius: 100%;
  width: 200px;
  height: 200px;
  cursor: pointer;
}
.social-icons {
  margin-top: 25px;
}
.social-icons a {
  font-size: 25px;
  margin: 15px;
  color: rgba(0, 0, 0, 0.712);
}
.social-icons a:hover {
  color: #000;
}
.intro {
  font-size: 45px;
  font-weight: bolder;
  text-align: left;
  margin-left: 20px;
  margin-top: 20px;
  /* color: #000; */
}
/* for mobile devices */
@media screen and (max-width: 420px) {
  .row {
    margin-top: 0px;
  }
  img {
    width: 150px;
    height: 150px;
  }
  .intro {
    font-size: 30px;
    font-weight: bold;
  }
}
.btn-primary {
  background-color: #f00;
  border-color: #f00;
}
.btn-primary:hover {
  background-color: rgb(240, 0, 0);
  border-color: rgb(240, 0, 0);
}
</style>
