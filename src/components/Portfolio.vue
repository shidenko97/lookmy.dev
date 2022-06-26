<template>
    <div class="portfolio-block">

        <BlockHeader description="Projects I've worked on" name="Portfolio"/>

        <div class="container">
            <div class="row portfolio-item">
                <div class="col-md-6">
                    <img :src="require('../assets/images/portfolio/crm.jpg')" alt=""/>
                </div>
                <div class="col-md-6">
                    <div class="portfolio-title">CRM system</div>
                    <div class="portfolio-text">It's a CRM system for one of the
                        most popular microfinancial organisation in Ukraine. This
                        product contains a lot of various modules like application
                        and antifraud scoring system, payments management, client's
                        identification and plenty of API integrations.
                    </div>
                </div>
            </div>
            <div class="row portfolio-item">
                <div class="col-md-6 order-md-6">
                    <img :src="require('../assets/images/portfolio/github.jpg')" alt=""/>
                </div>
                <div class="col-md-6">
                    <div class="portfolio-title">OpenSource projects</div>
                    <div class="portfolio-text">ALL TIME I'M TRYING TO IMPROVE MY PROGRAMMING SKILLS,
                        TO INCREASE EXPERIENCE AND TO LEARN NEW TECHNIQUE. THE BEST METHOD TO DO IT IS
                        TO READ CODE OF OTHER DEVELOPERS AND TO TRY TO MAKE YOUR OWN CONTRIBUTION TO
                        POPULAR (AND NOT REALLY) REPOSITORIES. SO I'VE DID SOME CONTRIBUTIONS TO OPEN-SOURCE
                        PROJECTS AND DID MY OWN OPEN-SOURCE PROJECTS. YOU CAN SEE IT AT MY
                        <a href="https://github.com/shidenko97" rel="nofollow" target="_blank">GITHUB profile</a>.
                    </div>
                </div>
            </div>
            <div class="row portfolio-item">
                <div class="col-md-6">
                    <img :src="require('../assets/images/portfolio/paragone.png')" alt=""/>
                </div>
                <div class="col-md-6">
                    <div class="portfolio-title">Paragone.ai</div>
                    <div class="portfolio-text">PARTICIPATED IN DEVELOPMENT AND SUPPORT SOCIAL ADVERTISEMENT MANAGEMENT SYSTEM.
                        BASICALLY WORKED ON THE DATA SIDE OF IT AS A DATA ENGINEER, BUILT WHOLE ETL PIPELINES AND
                        MODIFIED EXISTED MODULES.
                    </div>
                </div>
            </div>
            <div class="row portfolio-item">
                <div class="col-md-6 order-md-6">
                    <img :src="require('../assets/images/portfolio/xn--90ahbrd5f.xn--j1amh.jpg')"
                         alt=""/>
                </div>
                <div class="col-md-6">
                    <div class="portfolio-title">Кешбек.укр</div>
                    <div class="portfolio-text">This project is own idea AND
                        DEVELOPMENT OF A
                        SERVICE CASHBACK FOR CITIZENS OF UKRAINE. All PROCESSES OF
                        MONITORING CONVERSIONS, ACCOUNTING OF FUNDS, PAYMENTS,
                        NOTIFICATIONS, ADDING NEW AREAS, etc. ARE ABSOLUTELY
                        AUTOMATED. Unfortunately, due to legal problems, the project
                        could not be launched.
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
  import BlockHeader from '@/components/BlockHeader';

  export default {
    name: 'Portfolio',
    components: {BlockHeader}
  }
</script>

<style scoped>
    .portfolio-item {
        margin-bottom: 100px;
    }

    .portfolio-item img {
        width: 100%;
    }

    .portfolio-title {
        font-size: 36px;
        margin-top: 30px;
        font-family: 'Fira Sans', sans-serif;
        line-height: 60px;
        font-weight: 900;
        padding-right: 25px;
        text-transform: uppercase;
        color: #aaa;
        border-bottom: 2px solid var(--danger);
        z-index: 8;
    }

    .portfolio-text {
        font-size: 18px;
        margin-top: 10px;
        font-family: 'Fira Sans', sans-serif;
        font-weight: 500;
        text-align: justify;
        text-transform: uppercase;
        color: #aaa;
    }

    .portfolio-text a {
        color: #aaa;
        text-decoration: underline;
    }

    @media screen and (max-width: 768px) {
        .portfolio-title {
            font-size: 28px;
        }

        .portfolio-text {
            font-size: 16px;
        }
    }
</style>