<template>
  <section id="hero">
    <div class="hero header-image" :class="{ 'is-primary': isPrimary }">
      <div class="hero-head">
        <nav-bar/>
      </div>
      <div class="hero-body">
        <div class="container has-text-centered">
          <div class="has-text-grey-lighter">
          <span>
            <p class="title is-4 is-spaced">Welcome</p>
          </span>
          <separator color="#ffffff"></separator>
          <span>
            <p class="subtitle is-5 is-spaced">About me?</p>
          </span>
          <span><p>-------------</p></span>
          <span>
            <p class="subtitle is-6 is-spaced">{{ headline }}</p>
          </span>
          <span>
            <p class="subtitle is-6 is-spaced">
              <i>{{ subtitle }}</i>
            </p>
          </span>
          <span>
            <p class="subtitle is-6 is-spaced">
              <b>{{ work }}</b>
            </p>
          </span>
           <span><p>-----------------------</p></span>
          <span>
            <p class="subtitle is-6 is-spaced">{{new2}}</p>
          </span>
          <span><p color>----------------------------</p></span>
          <span>
            <p class="subtitle is-6 is-spaced">{{new3}}</p>
          </span>
          <span><p color="#bbbbbb">---------------------------------</p></span>
        </div>
      </div>
      </div>

      <div class="hero-foot">
        <div class="container has-text-centered">
          <a v-scroll-to="'#skills'">
            <i class="fa fa-chevron-down scroll-down"></i>
          </a>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import NavBar from "./NavBar";

export default {
  name: "hero",
  components: {
    NavBar
  },
  data() {
    return {
      title: "Portfolio",
      headline: " I live to design,test and code.",
      subtitle: "-----------------",
      work:
        "'What am I working on?' Building ERC20 Tokens on Ethereum Blockchain.",
      new2: "'Employment?' Exploring full-time employment options.",
      new3: "Will I be able to relocate? Yes!",
      isPrimary: true
    };
  },

  methods: {
    navHandler() {
      const { innerHeight, scrollY } = window;
      this.isPrimary = scrollY + 52 < innerHeight;
    }
  },
  mounted() {
    sr.reveal("#hero .hero-body > .container *", 150);
    sr.reveal("#hero .hero-foot", 200);

    window.addEventListener("scroll", this.navHandler.bind(this));
  }
};
</script>

<style lang="scss" scoped>
@import "~vars";

#hero {
  position: relative;
  height: 100vh;
  width: 100vw;
  user-select: none;
}

.logotype {
  text-emphasis-color: white;
  justify-content: left;
  user-select: none;
  pointer-events: none;
  padding-bottom: 10px;
  max-width: 650px;
  margin: 0 auto;
}
.is-horizontal-center {
  justify-content: center;
}
.hero {
  .nav {
    background: transparentize($color: #ffffff, $amount: 0.6);
    position: fixed;
    left: 0;
    right: 0;
    transition: all ease 1.4s;
  }

  &.is-primary {
    .nav {
      background: transparentize($color: #000000, $amount: 0.8);
      box-shadow: none;
    }
  }
}

.header-image {
  background: linear-gradient(22deg, #202020 2%, #6a7174 50%, #f7f7f7 80%);
  position: absolute;
  height: 100%;
  width: 100%;
}

.hero-body {
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
  padding: 1rem;
}

.title {
  text-transform: uppercase;
}

.scroll-down {
  font-size: 26px;
  opacity: 0.9;
  transition: all ease-in 0.25s;
  padding-bottom: 3rem;

  &:hover {
    background: transparentize($color: #ffffff, $amount: 0);
    opacity: 0.4;
    transform: scale(2);
  }
}
</style>
