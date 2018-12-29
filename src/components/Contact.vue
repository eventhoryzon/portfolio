<template>

  <section id="contact" class="section">
    <link rel="stylesheet" href="https://use.fontawesome.com/releases/v5.6.3/css/all.css" integrity="sha384-UHRtZLI+pbxtHCWp1t77Bi1L4ZtiqrqD80Kn4Z8NTSRyMA2Fd33n5dQ8lWUE00s/" crossorigin="anonymous">
    <div class="container has-text-centered">
      <h2 class="title is-2">Contact</h2>
      <separator color="#bbbbbb"></separator>
      <h5 class="subtitle reveal is-5">
        Wanna chat more! Drop me a mail and ill get back to you.
      </h5>
      <div class="block reveal">
        <a class="button is-warning is-outlined is-large"
          :href="`mailto:${email}`">
            <span><div class="block">
            <b-icon icon="angle-double-right"></b-icon>
            <b-icon icon="envelope"></b-icon>
            <b-icon icon="angle-double-left"></b-icon>
        </div></span>
        </a>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'contact',
  data() {
    return {
      email: 'shazibali@icloud.com',
    };
  },
  mounted() {
    sr.reveal('#contact .reveal', 250);
  },
};
</script>
