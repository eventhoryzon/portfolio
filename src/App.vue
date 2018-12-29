<template>
  <div id="app" v-cloak>
    <hero></hero>
    <skills></skills>
    <contact></contact>
    <copyright></copyright>
  </div>
</template>


<script>
import Hero from "./components/Hero";
import Skills from "./components/Skills";
import Contact from "./components/Contact";
import Copyright from "./components/Copyright";

export default {
  name: "app",
  components: {
    Hero,
    Skills,
    Contact,
    Copyright
  }
};
</script>

<style lang="scss">
#app {
  height: 100%;
  width: 100%;
  overflow: hidden;
}
</style>
