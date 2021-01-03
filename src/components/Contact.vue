<template>
    <div class="contact-block">

        <BlockHeader description="For any questions" name="Contact me"/>

        <div class="container">
            <div class="row">
                <div class="col-md-6">
                    <p>shidenko97@gmail.com</p>
                    <p>+38(073)073-81-19</p>
                    <a href="https://github.com/shidenko97" rel="nofollow"
                       target="_blank"><i class="fa fa-github-square"></i></a>
                    <a href="https://www.linkedin.com/in/shidenko" rel="nofollow"
                       target="_blank"><i class="fa fa-linkedin-square"></i></a>
                    <a href="https://facebook.com/s.hidenko" rel="nofollow"
                       target="_blank"><i class="fa fa-facebook-square"></i></a>
                    <a href="https://www.instagram.com/s.hidenko/" rel="nofollow"
                       target="_blank"><i class="fa fa-instagram"></i></a>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
  import BlockHeader from '@/components/BlockHeader';

  export default {
    name: 'Contact',
    components: {BlockHeader}
  }
</script>

<style scoped>
    @import '../assets/css/icons.css';

    .contact-block {
        min-height: 100vh;
    }

    .contact-block .row {
        padding: 138px 0 0 0;
    }

    .contact-block p {
        color: #aaa;
        font-family: 'PT Sans Caption', sans-serif;
        font-size: 48px;
    }

    .contact-block p a {
        text-decoration: none;
        color: #aaa;
    }

    .contact-block i {
        color: #aaa;
        margin: 20px 20px 0 0;
        font-size: 48px;
        transition: all .35s ease-in-out;
    }

    .contact-block i:hover {
        color: #fff;
        transition: all .35s ease-in-out;
    }

    @media screen and (max-width: 768px) {
        .contact-block .row {
            padding: 50px 0;
            text-align: center;
        }

        .contact-block p {
            font-size: 24px;
        }

        .contact-block a:last-child i {
            margin-right: 0;
        }
    }
</style>