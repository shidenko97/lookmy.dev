<template>
    <div id="about-block">

        <BlockHeader description="General information" name="About me"/>

        <div class="container">
            <div class="row">
                <div class="col-md-6">
                    <div class="timeline">
                        <div class="timeline-container timeline-left">
                            <div class="timeline-content wow bounceInDown"
                                 data-wow-delay="0s">
                                <h2>2015</h2>
                                <p>Became PHP Junior developer at TEEDEX.NET</p>
                            </div>
                        </div>
                        <div class="timeline-container timeline-right">
                            <div class="timeline-content wow bounceInDown"
                                 data-wow-delay="0.2s">
                                <h2>2020</h2>
                                <p>Earned a Master's Degree in Software Engineering</p>
                            </div>
                        </div>
                        <div class="timeline-container timeline-left">
                            <div class="timeline-content wow bounceInDown"
                                 data-wow-delay="0.4s">
                                <h2>2021</h2>
                                <p>Data Engineer at Perion</p>
                            </div>
                        </div>
                        <div class="timeline-container timeline-right">
                            <div class="timeline-content wow bounceInDown"
                                 data-wow-delay="0.6s">
                                <h2>2022</h2>
                                <p>Software Engineer at EVO</p>
                            </div>
                        </div>
                        <div class="timeline-container timeline-left">
                            <div class="timeline-content wow bounceInDown"
                                 data-wow-delay="0.8s">
                                <h2>...</h2>
                                <p>To be continued...</p>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="col-md-6 text-justify about-text">
                    <p class="wow bounceInUp" data-wow-duration="1s">
                        Started my way as a developer with PHP programming language. During the
                        time went I collected more experience and was participated in different API integrations, system designing process and
                        leadership's tasks. Since 2021 I also tried myself as a Data Engineer and developed different
                        ETL pipelines and data lakes. Currently working as backend developer, creating scalable web applications and REST APIs.
                    </p>
                    <p class="wow bounceInUp" data-wow-duration="1s">
                        I'm extremely communicative man so prefer to work in a team with mutually knowledge sharing. Do like to work with a product, but also see something
                        interesting in other fields too. Always happy to be a part of open-source project,
                        to learn something new or to start own project with great idea (I have a lot of them). Have active life style and
                        desire to learn 'n develop something new, as well as adhere to the rule "Good code is beautiful
                        code" and try to follow to all requirements of the modern development process.
                    </p>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
  import BlockHeader from '@/components/BlockHeader';

  export default {
    name: 'About',
    components: {BlockHeader}
  }
</script>

<style scoped>
    #about-block {
        min-height: 100vh;
        background: var(--background);
    }

    #about-block .about-text {
        font-family: 'PT Sans Caption', sans-serif;
        font-size: 18px;
        letter-spacing: 1px;
        color: var(--text);
    }

    .timeline::after {
        content: '';
        position: absolute;
        width: 4px;
        background-color: var(--text);
        top: 0;
        bottom: 0;
        left: 50%;
        margin-left: -2px;
    }

    .timeline-container {
        padding: 0 40px;
        position: relative;
        background-color: inherit;
        width: 50%;
    }

    .timeline-container::after {
        content: '';
        position: absolute;
        width: 25px;
        height: 25px;
        right: -12px;
        background-color: var(--text);
        border: 4px solid var(--text);
        top: 26px;
        border-radius: 50%;
        z-index: 1;
    }

    .timeline-left {
        left: 0;
    }

    .timeline-right {
        left: 50%;
    }

    .timeline-right::after {
        left: -12px;
    }

    .timeline-content {
        padding: 0 10px;
        position: relative;
        border-radius: 6px;
        color: var(--text);
    }

    .timeline-container .timeline-content h2 {
        text-align: center;
        font-size: 24px;
        border-bottom: 1px solid var(--danger);
        padding-bottom: 10px;
    }

    .timeline-container .timeline-content p {
        text-align: center;
        font-size: 14px;
    }

    .timeline-container:nth-child(1)::after {
        border-color: var(--indigo);
    }

    .timeline-container:nth-child(2)::after {
        border-color: var(--blue);
    }

    .timeline-container:nth-child(3)::after {
        border-color: var(--info);
    }

    .timeline-container:nth-child(4)::after {
        border-color: var(--success);
    }

    .timeline-container:nth-child(5)::after {
        border-color: var(--warning);
    }

    @media screen and (max-width: 768px) {
        .timeline-container {
            padding: 0 10px;
        }

        .timeline-container::after {
            top: 26px;
        }

        #about-block .about-text {
            padding-top: 50px;
            font-size: 16px;
        }
    }
</style>

<style>
    @media screen and (max-width: 768px) {
        .particles-js-canvas-el {
            position: absolute;
            top: 0;
        }
    }
</style>