<template>
  <div>
    <div class="sidebar animated fadeInDown">
      <HomeCard />
      <footer class="footer border-gray-300 border-r-2">
        <div class="text-gray-500 text-xl">&copy 2016-present Jen Looper</div>
      </footer>
    </div>
    <div class="main">
      <div class="page-top animated fadeInDown">
        <Nav />
      </div>

      <div class="autopagerize_page_element">
        <div class="content">
          <component :is="layout"></component>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Nav from "@theme/components/Nav.vue";
import Footer from "@theme/components/Footer.vue";
import HomeLayout from "@theme/layouts/HomeLayout.vue";
import BasicLayout from "@theme/layouts/BasicLayout.vue";
import HomeCard from "@theme/components/HomeCard.vue";
import ArticleLayout from "@theme/layouts/ArticleLayout.vue";
import BlogLayout from "@theme/layouts/BlogLayout.vue";
import ContactLayout from "@theme/layouts/ContactLayout.vue";
import VideoLayout from "@theme/layouts/VideoLayout.vue";

export default {
  components: {
    Nav,
    Footer,
    HomeLayout,
    BasicLayout,
    HomeCard,
    BlogLayout,
    ContactLayout,
    VideoLayout,
    ArticleLayout,
  },
  computed: {
    layout() {
      return this.$page.frontmatter.layout || "HomeLayout";
    },
  },
};
</script>

<style lang="stylus">
@import '../styles/minimal.styl';
</style>
