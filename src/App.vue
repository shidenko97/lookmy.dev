<template>
    <div id="app">
        <Title/>
        <About/>
        <Skills/>
        <Portfolio/>
        <Contact/>
        <ScrollHelper/>
    </div>
</template>

<script>
  import smoothscroll from 'smoothscroll-polyfill';

  import Title from '@/components/Title.vue'
  import About from "@/components/About";
  import Skills from "@/components/Skills";
  import Portfolio from "@/components/Portfolio";
  import Contact from "@/components/Contact";
  import ScrollHelper from "@/components/ScrollHelper";

  import * as WOW from './assets/js/wow.min.js';

  export default {
    name: 'App',
    components: {
      Title,
      About,
      Skills,
      Portfolio,
      Contact,
      ScrollHelper,
    },
    mounted() {
      // kick off the polyfill!
      smoothscroll.polyfill();

      new WOW().init();
    },
  }
</script>

<style>
    @import './assets/css/bootstrap.min.css';
    @import './assets/css/animate.min.css';

    body {
        min-height: 200vh;
        background: #fff;
        --background: #1f1f1f;
        --text: #aaa;
        background: var(--background);
    }
</style>
