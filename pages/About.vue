<template>
  <div class="container animate__animated animate__fadeIn">
    <div class="row">
      <div class="col-md-6">
        <div class="about">
          <h1 class="line-after">About Me</h1>
          <h4 class="mt-4">Hola 👋</h4>
          <p>
            My name is <b>Ibrahim Ogunbiyi</b> but you can call me <b>Geek</b>. I'm a <b>Data Scientist</b> and a <b>Technical Writer</b>.
            I'm currently studying computer science at the Prestigious Ondo State University <u>OAUSTECH</u> in Nigeria.
          </p>
            <p>I love applying my knowledge of statistics, programming language and machine learning
             to help me drive at a better business solution and I also enjoy telling stories from data 
             by leveraging statistical summaries either numerically or through the use of any 
             powerful visualization tool I can get my hands on. Plus I'm an agile learner. I learn new stuff everyday</p>
          
          <h4 class="mt-5">Tech Stacks</h4>
          <p>Below are some of the technologies I use daily:</p>
          <div class="row animate__animated animate__fadeInUp mt-0">
            <div class="col-md-4">
              <ul class="p-0" style="list-style-type: circle;">
              <h5>Programming Language</h5>
                <li>Python.</li>
                <li>MySQL.</li>
                <li>HTML&CSS.</li>
              </ul>
            </div>
            <div class="col-md-4">
              <h5>Libraries / Framework</h5>
              <ul class="p-0" style="list-style-type: circle;">
                <li>Scikit-Learn</li>
                <li>NLTK and RE library</li>
                <li>Pandas</li>
                <li>Numpy</li>
                <li>Seaborn,Matplotlib,and Plotly</li>
              </ul>
            </div>
            <div class="col-md-4">
              <h5>Visulization Tools</h5>
              <ul class="p-0" style="list-style-type: circle;">
                <li>Power BI</li>
                <li>Tableau</li>
              </ul>
            </div>
          </div>
        </div>
      </div>
      <div class="col-md-6">
        <img
          src="@/assets/working.png"
          alt="About Illustration"
          class="abt-img"
        />
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      startYear: 2017,
      currYear: new Date().getFullYear(),
      stacks: [
        {
          language: "HTML",
          experience: "3+ Years",
          variant: "secondary",
          breif: "lorem..."
        },
        {
          language: "CSS",
          experience: "3+ Years",
          variant: "primary",
          breif: "lorem..."
        },
        {
          language: "Javascript",
          experience: "2+ Years",
          variant: "warning",
          breif: "lorem..."
        },
        {
          language: "VUE.JS",
          experience: "2+ Years",
          variant: "success",
          breif: "lorem..."
        },
        {
          language: "Node.js",
          experience: "2+ Years",
          variant: "dark",
          breif: "lorem..."
        }
      ]
    };
  },
  // YOU'LL NEED TO UPDATE THIS FOR SEO (IN EVERY PAGE)
  head: {
    title: "About 🕵️‍♂️ - Ibrahim Ogunbiyi",
    meta: [
      {
        hid: "description",
        name: "description",
        // currYear - startYear
        content: `I love applying my knowledge of statistics, programming language and machine learning
             to help me drive at a better business solution and I also enjoy telling stories from data 
             by leveraging statistical summaries either numerically or through the use of any 
             powerful visualization tool I can get my hands on. Plus I'm an agile learner. I learn new stuff everyday.`
      }
    ]
  }
};
</script>
<style scoped>
.container {
  margin-top: 140px;
  text-align: left;
}
.line-after {
  overflow: hidden;
}
.line-after::after {
  content: "";
  display: inline-block;
  height: 0.5em;
  vertical-align: bottom;
  width: 100%;
  margin-right: -100%;
  margin-left: 10px;
  border-top: 2px solid rgb(211, 46, 46);
}
.abt-img {
  width: inherit;
  height: inherit;
  border-radius: 5px;
}
/* .abt-img:hover {
  animation: swing;
  animation-duration: 2s;
} */
ul.col-pro{
  border-style: none;
  background-color:aquamarine;
  width:500px;
  height: 200px;
  border-radius: 4%;

}
h5{
  font-size: 18px;
  margin: 0;
  padding: 0;
}
</style>
