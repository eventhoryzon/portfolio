<template>
  <section id="contact" class="section">
    <div class="container has-text-centered">
      <h2 class="title is-2">Contact</h2>
      <separator color="#18b6ff"></separator>
      <h5 class="subtitle reveal is-5">
        Wanna chat more! Drop me a mail and ill get back to you.
      </h5>
      <div class="block reveal">
        <a class="button grow is-dark"
          :href="`mailto:${email}`">
            <span>Click here !</span>
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
