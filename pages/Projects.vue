<template>
  <div class="about page  animate__animated animate__fadeIn">
    <h2>Recent Project</h2>
    <div class="container">
      <div class="row" v-for="(project, index) in projects" :key="index">
        <div class="col-md-5">
          <img
            :src="project.image_cover"
            :alt="project.title"
            class="project-cover"
          />
        </div>
        <div class="col-md-5">
          <h2 class="mt-3" style="text-align: left;">
            {{ project.title }}
            <hr class="dope" />
          </h2>
          <b-card class="mt-3 mb-3 text-left text-dark">
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
          title: "Car Price Prediction",
          tag: "Regression Model",
          description:
            "Built a Model using NLP and CatboostRegressor to Predict the Price of a Car",
          image_cover: require("@/assets/a.jpg"),
          github_url: "https://github.com/AsaoluElijah/qrcode",
          link: "https://asaoluelijah.github.io/qrcode/"
        },
        {
          title: "Customer Personality EDA",
          tag: "Progressive Web App",
          description:
            "Performed Exploratory Data Analysis to help Target which Group of Customers Precisely a Company will Recommend a Particular Product to.",
          image_cover: require("@/assets/CPA.jpg"),
          github_url: "https://github.com/ibrahim-ogunbiyi/Customer-Personal-Analysis-EDA/blob/main/Customer%20Segmentation%20EDA.ipynb",
          link: "https://github.com/ibrahim-ogunbiyi/Customer-Personal-Analysis-EDA"
          
        },
        {
          title: "Chronic Kidney Disease (CKD) ",
          tag: "Prediction of Chronic Disease Infection",
          description:
            "Performed Exloratory Data Analysis and Build a Predictive Model Using Random Forest to help Classify whether a Patient has CKD or not.",
          image_cover: require("@/assets/Ckd.jpg"),
          github_url: "https://github.com/ibrahim-ogunbiyi/Chronic-Kidney-Disease-CKD-Prediction/blob/main/CKD%20prediction.ipynb",
          link: "https://ibrahim-ogunbiyi-chronic-kidney-disease-ckd-predict-demo-eoim27.streamlitapp.com/"
        },
      ],
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
      },
      {
        hid: "og:title",
        name: "og:title",
        content: "Recent Projects 💻 - Asaolu Elijah"
      },
      {
        property: "og:description",
        content:
          "View all the recents open-sourced projects built with ♥ by Asaolu Elijah, open-sourced means this project source code are publicly available for everyone to use or modify."
      },
      {
        hid: "og:image",
        name: "og:image",
        content: require("@/assets/man-computer.png")
      }
    ]
  }
};
</script>
<style scoped>
.row {
  margin-top: 70px;
}
.project-cover {
  width: inherit;
  border-radius: 3px;
}
hr.dope {
  border: 0;
  width: 90px;
  border-top: 2px solid #dc3545;
  text-align: left;
  margin: initial;
  margin-top: 7px;
  margin-left: 5px;
}
img{
  height: initial;
}
</style>
