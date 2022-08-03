<template>
  <b-row style="margin-left: 0;margin-right: 0;">
    <b-col md="4">
      <b-img :src="avatar" id="avatar-img" alt="Asaolu Elijah Memoji" @mouseenter="changeAvatar"
        @mouseleave="changeAvatar" />
    </b-col>

    <b-col md="8">
      <h2 class="intro animate__animated animate__fadeInUp animate__fast">
        Hola 👋,
        <br />I<span>'m Ibrahim&nbsp;Ogunbiyi</span>.
      </h2>

      <div class="col-md-10 info">
        I'm an <b>Ardent Data Scientist</b> who loves breaking and fixing up stuff related to data,
        and clearly taking care of the data to give me insights as to what it is portraying.
        Along side my data science skills. I'm also a <b>Technical Writer</b> where I blog things on
        anything related to data.
        <br />
        <b-button class="action-btn animate__animated animate__wobble animate__delay-4s animate__fast" to="/projects">
          Explore >
        </b-button>

        <b-button class="action-btn" to="/contact" variant="primary">
          Get In Touch
        </b-button>

        <!-- .SOCIAL LINKS SECTION -->
        <div class="social-icons animate__animated animate__fadeInUp animate__delay-1s">
          <social-link :to="socialLinks.github">
            <GithubIcon />
          </social-link>

          <social-link :to="socialLinks.linkedin">
            <LinkedinIcon />
          </social-link>

          <social-link :to="socialLinks.twitter">
            <TwitterIcon />
          </social-link>

          <social-link :to="socialLinks.facebook">
            <FacebookIcon />
          </social-link>

          <social-link :to="socialLinks.mail">
            <MailIcon />
          </social-link>

          <social-link :to="socialLinks.youtube">
            <YoutubeIcon />
          </social-link>
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
import YoutubeIcon from "vue-ionicons/dist/logo-youtube.vue";
import MailIcon from "vue-ionicons/dist/md-mail.vue";

export default {
  components: {
    GithubIcon,
    LinkedinIcon,
    TwitterIcon,
    FacebookIcon,
    YoutubeIcon,
    MailIcon
  },

  data() {
    return {
      avatar: require("@/assets/avatar-1.webp"),
      // ADD YOUR SOCIAL LINKS HERE 👇
      socialLinks: {
        github: "https://github.com/ibrahim-ogunbiyi",
        linkedin: "https://www.linkedin.com/in/ibrahimogunbiyi/",
        twitter: "https://twitter.com/comejoinfolks",
        facebook: "",
        mail: "mailto:ibrahimabayomi234@gmail.com",
        youtube: ""
      }
    };
  },

  head: {
    title: "Portfolio 📊 - Ibrahim Ogunbiyi",
    meta: [
      {
        hid: "description",
        name: "description",
        content:
          `I love applying my knowledge of statistics, programming language and machine learning
             to help me drive at a better business solution and I also enjoy telling stories from data 
             by leveraging statistical summaries either numerically or through the use of any 
             powerful visualization tool I can get my hands on. Plus I'm an agile learner. I learn new stuff everyday.`
      },
      {
        hid: "og:title",
        name: "og:title",
        content: "Portfolio 📊 - Ibrahim Ogunbiyi"
      },
      {
        property: "og:description",
        content:
          `I love applying my knowledge of statistics, programming language and machine learning
             to help me drive at a better business solution and I also enjoy telling stories from data 
             by leveraging statistical summaries either numerically or through the use of any 
             powerful visualization tool I can get my hands on. Plus I'm an agile learner. I learn new stuff everyday.`
      },
      {
        hid: "og:image",
        name: "og:image",
        content: require("@/assets/coding.png")
      }
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
