<template>
    <span id="scroll-block">
        <span class="to-bottom" id="to-bottom">
            <span></span>
        </span>
        <span class="to-top hide" id="to-top">
            <span class="arrow bounceAlpha first next"></span>
            <span class="arrow bounceAlpha second next"></span>
        </span>
    </span>
</template>

<script>
  export default {
    name: 'ScrollHelper',
    mounted() {
      let scrollVar = window.innerHeight;
      let scroll_block = document.querySelector('#scroll-block');
      let to_top_el = document.querySelector('#to-top');
      let to_bottom_el = document.querySelector('#to-bottom');
      let scroll_limit = 150;

      window.addEventListener('scroll', () => {
        if (document.body.scrollTop > scroll_limit || document.documentElement.scrollTop > scroll_limit) {
          scrollVar = 0;

          to_top_el.classList.remove('hide');
          to_bottom_el.classList.add('hide');
        } else {
          scrollVar = window.innerHeight;

          to_top_el.classList.add('hide');
          to_bottom_el.classList.remove('hide');
        }
      });

      scroll_block.addEventListener('click', () => {
        window.scroll({top: scrollVar, left: 0, behavior: 'smooth'});
      });
    }
  }
</script>

<style scoped>
    #scroll-block {
        opacity: 0.8;
        position: fixed;
        right: 30px;
        bottom: 40px;
        z-index: 9999;
        color: var(--text);
        width: 50px;
        height: 62px;
        cursor: pointer;
    }

    #scroll-block .to-bottom {
        position: relative;
        margin: 10px 0 0 10px;
        box-sizing: border-box;
        border: 2px solid var(--text);
        border-radius: 23px;
        width: 30px;
        height: 42px;
        display: block;
        transition: opacity 0.7s;
    }

    #scroll-block .to-bottom span {
        position: absolute;
        display: block;
        top: 29%;
        left: 50%;
        width: 4px;
        height: 8px;
        -webkit-transform: translateX(-50%);
        transform: translateX(-50%);
        background: var(--text);
        border-radius: 25%;
        -webkit-animation: ani-mouse 2.5s linear infinite;
        animation: ani-mouse 2.5s linear infinite;
    }

    @-webkit-keyframes ani-mouse {
        0% {
            opacity: 1;
            top: 29%
        }
        15% {
            opacity: 1;
            top: 50%
        }
        50% {
            opacity: 0;
            top: 50%
        }
        100% {
            opacity: 0;
            top: 29%
        }
    }

    @-moz-keyframes ani-mouse {
        0% {
            opacity: 1;
            top: 29%
        }
        15% {
            opacity: 1;
            top: 50%
        }
        50% {
            opacity: 0;
            top: 50%
        }
        100% {
            opacity: 0;
            top: 29%
        }
    }

    @keyframes ani-mouse {
        0% {
            opacity: 1;
            top: 29%
        }
        15% {
            opacity: 1;
            top: 50%
        }
        50% {
            opacity: 0;
            top: 50%
        }
        100% {
            opacity: 0;
            top: 29%
        }
    }

    #scroll-block .to-top {
        width: 40px;
        height: 31px;
        margin-top: 4px;
        transform: rotate(270deg);
        -webkit-transform: rotate(270deg);
        position: absolute;
        top: 0;
        display: block;
        transition: opacity 0.7s;
    }

    #scroll-block .to-top .arrow {
        position: absolute;
        bottom: 0;
        margin-left: 0;
        width: 12px;
        height: 12px;
        background-size: contain;
        top: 15px;
    }

    #scroll-block .to-top .second {
        margin-left: 8px;
    }

    #scroll-block .to-top .next {
        background-image: url(data:image/svg+xml;base64,PHN2ZyBpZD0iTGF5ZXJfMSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIiB2aWV3Qm94PSIwIDAgNTEyIDUxMiI+PHN0eWxlPi5zdDB7ZmlsbDojZmZmfTwvc3R5bGU+PHBhdGggY2xhc3M9InN0MCIgZD0iTTMxOS4xIDIxN2MyMC4yIDIwLjIgMTkuOSA1My4yLS42IDczLjdzLTUzLjUgMjAuOC03My43LjZsLTE5MC0xOTBjLTIwLjEtMjAuMi0xOS44LTUzLjIuNy03My43UzEwOSA2LjggMTI5LjEgMjdsMTkwIDE5MHoiLz48cGF0aCBjbGFzcz0ic3QwIiBkPSJNMzE5LjEgMjkwLjVjMjAuMi0yMC4yIDE5LjktNTMuMi0uNi03My43cy01My41LTIwLjgtNzMuNy0uNmwtMTkwIDE5MGMtMjAuMiAyMC4yLTE5LjkgNTMuMi42IDczLjdzNTMuNSAyMC44IDczLjcuNmwxOTAtMTkweiIvPjwvc3ZnPg==);
    }

    @keyframes bounceAlpha {
        0% {
            opacity: 1;
            transform: translateX(0px) scale(1);
        }
        25% {
            opacity: 0;
            transform: translateX(10px) scale(0.9);
        }
        26% {
            opacity: 0;
            transform: translateX(-10px) scale(0.9);
        }
        55% {
            opacity: 1;
            transform: translateX(0px) scale(1);
        }
    }

    #scroll-block .to-top .bounceAlpha {
        animation-name: bounceAlpha;
        animation-duration: 3.4s;
        animation-iteration-count: infinite;
        animation-timing-function: linear;
    }

    #scroll-block .to-top .arrow.first.bounceAlpha {
        animation-name: bounceAlpha;
        animation-duration: 3.4s;
        animation-delay: 0.2s;
        animation-iteration-count: infinite;
        animation-timing-function: linear;
    }

    .hide {
        opacity: 0;
        transition: opacity 0.7s;
    }

    @media screen and (max-width: 768px) {
        #scroll-block {
            right: 15px;
            bottom: 15px;
        }
    }
</style>

<style>
    html {
        scroll-behavior: smooth;
    }
</style>