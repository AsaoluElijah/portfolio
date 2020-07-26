<template>
  <div class="about page  animate__animated animate__fadeIn">
    <h2>Recent Project</h2>
    <div class="container">
      <div class="row mt-5" v-for="(project, index) in projects" :key="index">
        <div class="col-md-6">
          <img :src="project.image_cover" alt="" style="width: inherit;" />
        </div>
        <div class="col-md-6">
          <h2 class="mt-3" style="text-align: left;">{{ project.title }} <hr class="dope"> </h2>
          <b-card class="mt-5 mb-3">
            <p>{{ project.description }}</p>
            <b-link :href="project.link"
              >Check it out! <LinkIcon style="color: #000;"
            /></b-link>
            <hr />
            <b-link :href="project.github_url"
              >View source code <GithubIcon style="color: #000;"
            /></b-link>
          </b-card>
        </div>
      </div>
      <!-- <div class="row">
        <div class="col-md-6" v-for="project in projects" :key="project.title">
          <b-card
            :title="project.title"
            :img-src="project.image_cover"
            img-alt="Image"
            img-top
            tag="article"
            class="mb-3"
          >
            <b-badge
              pill
              :variant="
                tagVariants[Math.floor(Math.random() * tagVariants.length)]
              "
              class="mb-3"
              >{{ project.tag }}</b-badge
            >
            <b-card-text v-html="project.description"> </b-card-text>
            <b-link :href="project.link"
              >Check it out! <LinkIcon style="color: #000;"
            /></b-link>
            <hr />
            <b-link :href="project.github_url"
              >View source code <GithubIcon style="color: #000;"
            /></b-link>
          </b-card>
        </div>
      </div> -->
    </div>
  </div>
</template>
<script>
import LinkIcon from "vue-ionicons/dist/md-link.vue";
import GithubIcon from "vue-ionicons/dist/logo-github.vue";
export default {
  components: {
    GithubIcon,
    LinkIcon
  },
  data() {
    return {
      projects: [
        {
          title: "Say-It",
          tag: "Progressive Web App",
          description:
            "Typing sucks, say the words instead and the text will be generated for you.",
          image_cover: require("@/assets/speak.jpg"),
          github_url: "https://github.com/AsaoluElijah/say-it/",
          link: "https://asaoluelijah.github.io/say-it"
        },
        {
          title: "Proton",
          tag: "Chrome-Extention, Coming Soon!",
          description:
            "Proton charges you with positivity when you open a new chrome tab, plus you also get worldwide latest info.",
          image_cover: require("@/assets/illustration.jpg"),
          github_url: "",
          link: ""
        },
        {
          title: "Qr-Generator",
          tag: "Progressive Web App",
          description:
            "Easily share secret messages with friends by converting text to qrcode.",
          image_cover: require("@/assets/qr-1.png"),
          github_url: "https://github.com/AsaoluElijah/qrcode",
          link: "https://asaoluelijah.github.io/qrcode/"
        }
      ]
    };
  },
  methods: {
    isEven(n) {
      if (n % 2 == 0) {
        return true;
      } else {
        return false;
      }
    }
  },
  head: {
    title: "Recent Projects 💻 - Asaolu Elijah",
    meta: [
      {
        hid: "description",
        name: "description",
        content:
          "View all the recents open-sourced projects built with ♥ by Asaolu Elijah, open-sourced means this project source code are publicly available for everyone to use or modify."
      }
    ]
  }
};
</script>
<style scoped>
.row {
  margin-top: 50px;
}
.card {
  color: #000;
}
.card-img-top {
  background: #ccc;
  /* width: auto;
  height: auto; */
  /* max-height: 220px; */
}
.card-body {
  text-align: left;
}
.card-title {
  text-align: center;
}
.card-text {
  font-size: 18px;
}
hr.dope{
  border: 0;
    width: 90px;
    border-top: 2px solid #dc3545;
    text-align: left;
    margin: initial;
    margin-top: 7px;
    margin-left: 5px;
}
</style>
