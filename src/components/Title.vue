<template>
    <div id="particles-js">
        <div class="container" style="position: relative;">
            <div class="title-block">
                <h1>I'm Serhii Hidenko</h1>

                <Typed :strings="[
                  'Software Engineer',
                  'Python developer',
                  'Master of googling'
                ]"/>

            </div>
            <p class="short-bio wow fadeInLeft">
                {{ age }} y.o., Middle Python Software Engineer at
                <a href="https://evo.company" rel="nofollow" target="_blank">EVO</a> with a solid background in
                Data Engineering. Guy with a strong understanding of software engineering concepts. Design and build
                scalable web-applications is my passion. More than {{ exp_years }} years experience in programming.
                Have a master's diploma in Software Engineering
                (NTUU "KPI").
            </p>
        </div>
    </div>
</template>

<script>
  import Typed from '@/components/Typed';

  import '../assets/js/particles.min.js';

  export default {
    name: 'Title',
    components: {Typed},
    data: () => ({
      birthday: new Date(1997, 8, 1),
      start_dev: new Date(2014, 4, 1),
    }),
    methods: {
      yearsSince(since) {
        let start_date = 1970;
        let now = new Date();

        return new Date(now - since).getFullYear() - start_date;
      },
    },
    computed: {
      age: function () {
        return this.yearsSince(this.birthday);
      },
      exp_years: function () {
        return this.yearsSince(this.start_dev);
      },
    },
    mounted() {
      // eslint-disable-next-line no-undef
      particlesJS('particles-js', require('../assets/particles'));
    },
  }
</script>

<style scoped>
    #particles-js {
        width: 100%;
        height: 100vh;
        background-color: var(--background);
        position: relative;
    }

    .title-block {
        position: absolute;
        top: 27vh;
        width: 50%;
        font-family: 'PT Sans Caption', sans-serif;
    }

    .title-block h1 {
        font-weight: 700;
        font-size: 60px;
        line-height: 60px;
        color: #fff;
    }

    .short-bio {
        position: absolute;
        top: calc(27vh + 270px);
        width: 50%;
        font-family: 'PT Sans Caption', sans-serif;
        font-size: 16px;
        line-height: 16px;
        letter-spacing: 2px;
        padding-right: 100px;
        color: #aaa;
    }

    .short-bio a {
        color: #aaa;
    }

    @media screen and (max-width: 768px) {
        .title-block {
            width: 100%;
            top: 0;
            position: relative;
            padding-top: 10vh;
        }

        .title-block h1 {
            font-size: 48px;
        }

        .short-bio {
            width: 100%;
            position: relative;
            margin-top: 10vh;
            text-align: justify;
            padding-right: 0;
            top: auto;
        }
    }
</style>