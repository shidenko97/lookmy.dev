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
                                <h2>2014</h2>
                                <p>Became interested in programming</p>
                            </div>
                        </div>
                        <div class="timeline-container timeline-right">
                            <div class="timeline-content wow bounceInDown"
                                 data-wow-delay="0.2s">
                                <h2>2015</h2>
                                <p>Hired to TEEDEX.NET as PHP developer</p>
                            </div>
                        </div>
                        <div class="timeline-container timeline-left">
                            <div class="timeline-content wow bounceInDown"
                                 data-wow-delay="0.4s">
                                <h2>2020</h2>
                                <p>Earned a Master's Degree in Software Engineering</p>
                            </div>
                        </div>
                        <div class="timeline-container timeline-right">
                            <div class="timeline-content wow bounceInDown"
                                 data-wow-delay="0.6s">
                                <h2>2021</h2>
                                <p>Started working at Perion</p>
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
                        Full-stack web developer with backend and API preferring.
                        Have a strong experience in PHP development, but since 2019
                        also actively interested in Python. Basically have
                        experience in web-developing, but always open for a new
                        directions of programming.
                    </p>
                    <p class="wow bounceInUp" data-wow-duration="1s">
                        Prefer to work in a team and to have a strong communications
                        with every member, to increase own and team skills and
                        produce perfect product. Have active life style and desire
                        to learn 'n develop something new, as well as adhere to the
                        rule "Good code is beautiful code" and try to follow to all
                        requirements of the modern development process.
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