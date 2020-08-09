<template>
  <b-container class="page  animate__animated animate__fadeIn">
    <h2>Recent Articles</h2>
    <p>
      Hosted with
      <sub>
        <HeartIcon animate="beat" style="color: red;font-size: 24px;" />
      </sub>
      on
      <em>
        <a href="https://dev.to/asaoluelijah" target="_blank" rel="noopener"
          >dev.to</a
        >
      </em>
      <br />
      <br />
      <b-alert
        show
        variant="danger"
        v-if="showErrALert"
        style="display: inline-block;"
      >
        Error loading articles, click
        <a href="https://dev.to/asaoluelijah" target="_blank">here</a> to read
        'em instaed.
      </b-alert>
      <b-spinner variant="primary" v-if="showLoader"></b-spinner>
    </p>
    <b-row class="articles" v-if="blogs.length > 0">
      <div class="col-md-6" v-for="blog in blogs" :key="blog.id">
        <div>
          <b-card-group deck>
            <b-card
              :img-src="blog.image"
              :img-alt="blog.imgAlt"
              img-top
              tag="article"
              class="mb-2"
            >
              <h4>{{ blog.title }}</h4>
              <b-badge
                class="animate__animated animate__fadeInUp"
                style="margin: 2px;"
                v-for="tag in blog.tags"
                :key="tag"
                pill
                :variant="
                  tagVariants[Math.floor(Math.random() * tagVariants.length)]
                "
                >#{{ tag }}</b-badge
              >
              <hr />
              <b-card-text>{{ blog.desc }}</b-card-text>

              <b-button
                :href="blog.url"
                target="_blank"
                rel="noopener"
                variant="default"
                >Read More..</b-button
              >
            </b-card>
          </b-card-group>
        </div>
      </div>
    </b-row>
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
      tagVariants: ["primary", "success", "warning", "info", "dark", "danger"],
      blogs: []
    };
  },
  head: {
    title: "Recent Articles 📚 - Asaolu Elijah",
    meta: [
      {
        hid: "description",
        name: "description",
        content:
          "Read articles written by Asaolu Elijah, articles include topics under web development (html, css, javascript), mobile app development and many more."
      },
      {
        hid: "og:title",
        name: "og:title",
        content: "Recent Articles 📚 - Asaolu Elijah"
      },
      {
        property: "og:description",
        content: "Read articles written by Asaolu Elijah, articles include topics under web development (html, css, javascript), mobile app development and many more."
      },
    ]
  },
  methods: {
    // get articles hosted on dev.to
    getArticles(username, success, error) {
      let articleImage;
      fetch("https://dev.to/api/articles?username=" + username)
        .then(res => res.json())
        .then(data => {
          data.forEach(article => {
            if (/(hcti.io)/.test(article.image) == true) {
              // use random image from lorem picsum
              articleImage = "https://picsum.photos/600/400";
            } else {
              articleImage = article.social_image;
            }
            this.blogs.push({
              id: article.id,
              title: article.title,
              desc: article.description,
              image: articleImage,
              url: article.url,
              date: article.readable_publish_date,
              tags: article.tag_list,
              imgAlt: article.title + " - Asaolu Elijah"
            });
          });
          success();
        })
        .catch(err => {
          error();
          console.log("Error fetching articles " + err);
        });
    }
  },
  mounted() {
    this.getArticles(
      "asaoluelijah",
      () => {
        this.showLoader = false;
      },
      () => {
        this.showErrALert = true;
        this.showLoader = false;
      }
    );
  }
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
</style>
