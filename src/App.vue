<template>
  <div id="app">
    <h1>{{ title }}</h1>
    <h1>After computed: {{ lowerCaseTitle }}</h1>
    <button @click="show" ref="infoButton">Show</button>
    <p v-if="showParagraph">
      Vue (pronounced /vju:/, like view) is a JavaScript framework for building
      user interfaces. It builds on top of standard HTML, CSS and JavaScript,
      and provides a declarative and component-based programming model that
      helps you efficiently develop user interfaces, be it simple or complex.
    </p>
  </div>
</template>

<script>
// v-if se remove phan tu di, con v-show se an phan tu di

export default {
  name: "App",
  data() {
    return { title: "VueJS", showParagraph: false };
  },
  methods: {
    show: function () {
      this.showParagraph = !this.showParagraph;
      this.updateTitle("This VueJS Instace (Updated)");
      console.log(this.$refs);
      this.$refs.infoButton.innerText = "Hello";
      // innerText ko co kha nang ghi de len template
    },
    updateTitle: function (title) {
      this.title = title;
    },
  },
  watch: {
    title: function (value) {
      alert("Title changed, new value: " + value);
    },
  },
  computed: {
    lowerCaseTitle: function () {
      return this.title.toLowerCase();
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
