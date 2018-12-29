<template>
  <footer class="footer">
    <div class="container">
      <div class="content has-text-centered">
        <p class="reveal">
          © 2018 Shazib Ali
        </p>
        <p class="reveal">
          <a class="icon"
            v-for="item in social"
            :href="item.link"
            :key="item.id"
            target="_blank"
            rel="noopener">
            <b-icon :icon="item.icon"></b-icon>
          </a>
        </p>
      </div>
    </div>
  </footer>
</template>

<script>
export default {
  name: "copyright",
  mounted() {
    sr.reveal(".footer .reveal", 200);
  },
  data() {
    return {
      social: [
        {
          icon: "facebook",
          link: "https://www.facebook.com/"
        },
        {
          icon: "linkedin",
          link: "https://linkedin.com/in/he77y"
        },
        {
          icon: "twitter",
          link: "https://twitter.com/he77y"
        },
        {
          icon: "google-plus",
          link: "https://plus.google.com/+shazibali"
        },
        {
          icon: "github-square",
          link: "https://github.com/he77y"
        }
      ]
    };
  }
};
</script>