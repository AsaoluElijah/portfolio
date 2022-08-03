<template>
  <b-container class="page  animate__animated animate__fadeIn">
    <h2>
      Top Articles Written by Me
    </h2>
    <b-row class="articles" v-if="blogs.length > 0">
      <div class="col-md-4 mb-3" v-for="(blog, id) in blogs" :key="id">
        <div>
          <b-card-group deck>
            <b-card :img-src="blog.cover_photo" :img-alt="blog.title" img-top tag="article" class="mb-2">
              <h4>{{ blog.title }}</h4>
              <b-badge class="animate__animated animate__fadeInUp" style="margin: 2px;" v-for="tag in blog.tags"
                :key="tag" pill :variant="
                  tagVariants[Math.floor(Math.random() * tagVariants.length)]
                ">#{{ tag }}</b-badge>
              <hr />
              <b-card-text>{{ blog.desc }}</b-card-text>

              <b-button :href="blog.url" target="_blank" rel="noopener" variant="default">Read More..</b-button>
            </b-card>
          </b-card-group>
        </div>
      </div>
    </b-row>
    <p class="mt-3">Click Here for More to View My Writing <a href="https://linktr.ee/ibrahimwriting">Portforlio</a></p>
  </b-container>
</template>
<script>
import HeartIcon from "vue-ionicons/dist/md-heart.vue";
export default {
  components: { HeartIcon },
  data() {
    return {
      showLoader: true,
      showErrALert: false,
      tagVariants: ["primary", "success", "warning", "info", "dark"],
      blogs: [{
        title: 'Top Stats Concepts to Know Before Getting into Data Science',
        desc: "If you want to get started into Data Science and don't have any Statiscal background you should definetely check this article out.",
        url: 'https://www.freecodecamp.org/news/top-statistics-concepts-to-know-before-getting-into-data-science/',
        cover_photo: 'https://user-images.githubusercontent.com/73393430/182646490-4e491b97-aa19-4f2f-9ca9-eb6ef0305439.jpg',
        tags: ['ML', 'Statistics', 'DS']
      }, {
        title: 'How to Scrape Data from Twitter using Tweepy and Snscrape',
        desc: 'Learn How to Scrape Data from Twitter using two Popular Libraries Tweepy and Snscrape',
        url: 'https://www.freecodecamp.org/news/python-web-scraping-tutorial/',
        cover_photo: 'https://user-images.githubusercontent.com/73393430/182649137-18d7b0b6-2765-4150-841c-638208ae0b03.jpg',
        tags: ['ML', 'Python', 'AI']
      }, {
        title: 'Keep Track of Machine Learning Experiments With Comet.',
        desc: 'Comet.ML is an ML Experimentation Platform that Allows you to Keep Track of your ML Models experiments.',
        url: 'https://medium.com/cometheartbeat/keep-track-of-machine-learning-experiments-with-comet-c96e28c3352e',
        cover_photo: 'https://user-images.githubusercontent.com/73393430/182648089-755743cf-51fd-4685-873d-535a09559fef.jpg',
        tags: ['ML', 'AI', 'DS']
      }]
    };
  },
  head: {
    title: "Recent Articles 📚 - Ibrahim Ogunbiyi",
    meta: [
      {
        hid: "description",
        name: "description",
        content:
          "Read articles written by Ibrahim Ogunbiyi, articles revolves around anything data centric Data Science, Machnine Learning, Python and many more."
      },
      {
        hid: "og:title",
        name: "og:title",
        content: "Recent Articles 📚 - Ibrahim Ogunbiyi"
      },
      {
        property: "og:description",
        content:
          "Read articles written by Ibrahim Ogunbiyi, articles revolves around anything data centric Data Science, Machnine Learning, Python and many more."
      },
    ]
  },
};
</script>
<style scoped>
.container {
  margin-top: 120px;
}

.row {
  margin-top: 40px;
}

.spinner-border {
  margin-top: 40px;
}

.card {
  text-align: left;
  color: #000;
}

img {
  border-radius: initial;
  height: initial;
}
</style>
