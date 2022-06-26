<template>
    <div class="skills-block">

        <BlockHeader description="Achievements and experience" name="Skills"/>

        <div class="container">
            <div class="row skills" id="skills">
                <div class="col-md-3">
                    <div id="skill1"></div>
                </div>
                <div class="col-md-3">
                    <div id="skill2"></div>
                </div>
                <div class="col-md-3">
                    <div id="skill3"></div>
                </div>
                <div class="col-md-3">
                    <div id="skill4"></div>
                </div>
            </div>
            <div class="row">
                <div class="col-md-12">
                    <Swiper :images="[
                      {
                        alt: 'SoftServe Python Integration',
                        title: 'SoftServe Python Integration',
                        src: require('../assets/images/certs/SoftServePythonIntegration.jpg'),
                      },
                      {
                        alt: 'SoftServe Python WEB',
                        title: 'SoftServe Python WEB',
                        src: require('../assets/images/certs/Certificate.jpg'),
                      },
                      {
                        alt: 'ITEA Python Advanced',
                        title: 'ITEA Python Advanced',
                        src: require('../assets/images/certs/itea-python-advanced.png'),
                      },
                      {
                        alt: 'SoftServe English Evaluation',
                        title: 'SoftServe English Evaluation',
                        src: require('../assets/images/certs/Certificate-1.jpg'),
                      },
                      {
                        alt: 'NVIDIA DLI FUNDAMENTALS OF ACCELERATED COMPUTING WITH CUDA PYTHON',
                        title: 'NVIDIA DLI FUNDAMENTALS OF ACCELERATED COMPUTING WITH CUDA PYTHON',
                        src: require('../assets/images/certs/nv-dli-cuda-python.jpg'),
                      },
                      {
                        alt: 'NVIDIA DLI FUNDAMENTALS OF ACCELERATED COMPUTING WITH CUDA C/C++',
                        title: 'NVIDIA DLI FUNDAMENTALS OF ACCELERATED COMPUTING WITH CUDA C/C++',
                        src: require('../assets/images/certs/nv-dli-cuda-c.jpg'),
                      },
                      {
                        alt: 'NVIDIA DLI FUNDAMENTALS OF DEEP LEARNING FOR COMPUTER VISION',
                        title: 'NVIDIA DLI FUNDAMENTALS OF DEEP LEARNING FOR COMPUTER VISION',
                        src: require('../assets/images/certs/nv-dli-cv.jpg'),
                      },
                      {
                        alt: 'MongoDB Basics',
                        title: 'MongoDB Basics',
                        src: require('../assets/images/certs/mongodb-basics.jpeg'),
                      },

                      {
                        alt: 'Coursera Version Control with Git',
                        title: 'Coursera Version Control with Git',
                        src: require('../assets/images/certs/coursera-git.jpg'),
                      },

                      {
                        alt: 'Coursera System Administration and IT Infrastructure Services',
                        title: 'Coursera System Administration and IT Infrastructure Services',
                        src: require('../assets/images/certs/coursera-sysadm.jpg'),
                      },
                      {
                        alt: 'Coursera Cloud Computing Basics',
                        title: 'Coursera Cloud Computing Basics',
                        src: require('../assets/images/certs/coursers-cloud-computing-basics.jpg'),
                      },
                      {
                        alt: 'GeekBrains Python',
                        title: 'GeekBrains Python',
                        src: require('../assets/images/certs/gb-python.jpg'),
                      },
                      {
                        alt: 'GeekBrains PHP',
                        title: 'GeekBrains PHP',
                        src: require('../assets/images/certs/gb-php.jpg'),
                      },
                      {
                        alt: 'GeekBrains HTML&CSS',
                        title: 'GeekBrains HTML&CSS',
                        src: require('../assets/images/certs/gb-html-css.jpg'),
                      },
                      {
                        alt: 'GeekBrains Javascript',
                        title: 'GeekBrains Javascript',
                        src: require('../assets/images/certs/gb-js.jpg'),
                      },
                    ]"/>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
  import BlockHeader from '@/components/BlockHeader';
  import Swiper from '@/components/Swiper';

  import * as ProgressBar from '../assets/js/progressbar.min.js';

  export default {
    name: 'Skills',
    components: {Swiper, BlockHeader},
    data: () => ({
      skills_config: [
        {
          id: '#skill1',
          color: '#c8a2c8',
          from: '#b0b3d6',
          to: '#c8a2c8',
          text: 'Backend <small>FastAPI, Flask, AIOHTTP</small><small>and others</small>',
          value: 0.80,
        },
        {
          id: '#skill2',
          color: '#f16529',
          from: '#e44d26',
          to: '#f16529',
          text: 'Data Engineering <small>Pandas, Airflow</small><small>NumPy, PySpark</small>',
          value: 0.75,
        },
        {
          id: '#skill3',
          color: '#4797d0',
          from: '#549eff',
          to: '#4797d0',
          text: 'Databases <small>Relational, Key-Value, </small><small>Document-oriented</small>',
          value: 0.60,
        },
        {
          id: '#skill4',
          color: '#f0a91e',
          from: '#9ece26',
          to: '#f0a91e',
          text: 'Cloud development <small>AWS, Docker, git, K8s</small><small>with auto-deployment</small>',
          value: 0.45,
        },
      ],
      progress_bars: [],
      skills_duration: 800,
    }),
    mounted() {

      for (let config of this.skills_config) {
        this.progress_bars.push({
          widget: new ProgressBar.Circle(config.id, {
            color: config.color,
            trailColor: 'rgba(255, 255, 255, 0.1)',
            trailWidth: 1,
            duration: 1400,
            easing: 'bounce',
            strokeWidth: 6,
            from: {
              color: config.from,
              a: 0
            },
            to: {
              color: config.to,
              a: 1
            },
            step: function (state, circle) {
              circle.path.setAttribute('stroke', state.color);
            },
            text: {
              value: config.text,
              className: 'skills-label',
              style: {
                color: config.color,
                position: 'absolute',
                left: '50%',
                top: '50%',
                align: 'center',
                width: '100%',
                padding: 0,
                margin: 0,
                fontSize: '20px',
                transform: {
                  prefix: true,
                  value: 'translate(-50%, -50%)'
                }
              },
              autoStyleContainer: true,
              alignToBottom: true
            }
          }),
          expected_value: config.value
        });
      }

      window.addEventListener('scroll', () => {
        if (
          (document.querySelector('html').scrollTop + window.innerHeight - 100) >=
          document.querySelector('#skills').offsetTop
        ) {

          for (let progress_bar of this.progress_bars) {
            if (progress_bar.widget.value() <= 0.000001) {  // Temporally bug of progressbar.js
              progress_bar.widget.animate(progress_bar.expected_value, {
                duration: this.skills_duration
              });
            }
          }

        }
      });
    },
  }
</script>

<style scoped>
    .skills-block {
        background: var(--background);
        min-height: 100vh;
    }

    #skill1, #skill2, #skill3, #skill4 {
        margin: 20px;
        width: 200px;
        height: 200px;
    }

    .skills {
        margin-bottom: 100px;
    }

    @media screen and (max-width: 768px) {
        .skills {
            margin-bottom: 50px;
        }

        #skill1, #skill2, #skill3, #skill4 {
            margin: 10px auto 40px auto;
        }
    }
</style>

<style>
    .skills-label {
        text-align: center;
    }

    .skills-label small {
        font-size: 11px;
        display: block;
    }
</style>