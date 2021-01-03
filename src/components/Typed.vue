<template>
    <span id="typed"></span>
</template>

<script>
  import * as Typed from '../assets/js/typed.min';

  export default {
    name: 'Typed',
    props: ['strings'],
    mounted() {
      new Typed('#typed', {
        strings: this.strings,
        typeSpeed: 50,
        startDelay: 500,
        backSpeed: 10,
        loop: true,
        autoInsertCss: false
      });
    }
  }
</script>

<style scoped>
    #typed {
        font-size: 20px;
        line-height: 20px;
        opacity: 0.8;
        color: var(--danger);
    }

    .typed-cursor {
        opacity: 0.8;
        color: var(--danger);
    }

    .typed-cursor.typed-cursor--blink {
        animation: typedjsBlink 0.7s infinite;
        -webkit-animation: typedjsBlink 0.7s infinite;
    }

    @keyframes typedjsBlink {
        50% {
            opacity: 0.0;
        }
    }

    @-webkit-keyframes typedjsBlink {
        0% {
            opacity: 1;
        }
        50% {
            opacity: 0.0;
        }
        100% {
            opacity: 1;
        }
    }

    @media screen and (max-width: 768px) {
        .title-block #typed {
            font-size: 18px;
        }
    }
</style>