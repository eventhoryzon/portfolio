<template>
  <header class="nav">
    <div class="container">
      <div class="nav-left">
        <a class="nav-item" v-scroll-to="'#hero'">
          <span>
            <img :src="image" :alt="logo">
          </span>
          <span>
            <p class="subtitle is-6"></p>
          </span>
        </a>
      </div>
      <span
        class="nav-toggle"
        :class="{'is-active' : isExpanded }"
        @click="isExpanded = !isExpanded"
      >
        <span></span>
        <span></span>
        <span></span>
      </span>
      <div class="nav-right nav-menu" :class="{ 'is-active': isExpanded }">
        <a
          v-for="item in menuItems"
          v-bind:key="item.id"
          class="nav-item"
          @click.prevent="goTo(item)"
        >{{ item.title }}</a>
      </div>
    </div>
  </header>
</template>

<script>
import * as images from "../assets/img/skills";

export default {
  name: "navbar",
  data() {
    return {
      logo: "Shazib Ali",
      image: images.Logo,
      isExpanded: false,
      menuItems: [
        {
          title: "Skills",
          el: "#skills"
        },
        {
          title: "Resume",
          url:
            "https://drive.google.com/file/d/1gKCTket3r_bgSjjVxUfJthxdCoDa70Uw/view?usp=sharing"
        },
        {
          title: "Contact",
          el: "#contact"
        },
        {
          title: "Speedtest",
          url: "http://shazibali.speedtestcustom.com"
        }
      ]
    };
  },
  methods: {
    goTo(item) {
      this.isExpanded = false;
      if (item.url) {
        window.open(item.url);
      } else {
        this.$scrollTo(item.el);
      }
    }
  }
};
</script>

<style lang="scss" scoped>
</style>
