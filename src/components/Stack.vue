<script setup>
import Chart from 'primevue/chart';
import 'primevue/resources/themes/lara-dark-indigo/theme.css'

</script>

<template>
  <section id="stack">
    <p class="primary">My skills</p>
    <div class="split">
      <Chart type="bar" :data="charts.frontend.data" :options="charts.frontend.options" />
      <Chart type="bar" :data="charts.backend.data" :options="charts.backend.options" />
    </div>
    <Chart type="bar" :data="charts.tools.data" :options="charts.tools.options" />
  </section>
</template>
<script>
  export default {
    data() {
      return {
        charts: {
          frontend: {
            data: {
              labels: ['HTML', 'CSS', 'Vue 3', 'SCSS', 'Vue 2', 'React', 'jQuery', 'webGL', 'THREE.JS', 'SASS'],
              datasets: [
                {
                    label: 'Frontend',
                    backgroundColor: '#fa8e42',
                    data: [100, 100, 100, 100, 100, 90, 85, 70, 60, 60, 30],
                },
              ],
            },
            options: {
              responsive: true,
              maintainAspectRatio: false,
              indexAxis: 'y',
              scales: {
                x: {
                  ticks: {
                    callback: function(val, index) {
                      return '';
                    },
                    color: 'red',
                  },
                },
              }
            }
          },
          backend: {
            data: {
              labels: ['PHP', 'Laravel', 'Python', 'SQL', 'Opencart 2/3', 'Nuxt', 'Wordpress', 'Tilda', 'Symfony', 'Shopify'],
              datasets: [
                {
                    label: 'Backend',
                    backgroundColor: '#42A5F5',
                    data: [100, 100, 90, 90, 85, 65, 60, 60, 30, 30],
                },
              ],
            },
            options: {
              responsive: true,
              maintainAspectRatio: false,
              indexAxis: 'y',
              scales: {
                x: {
                  ticks: {
                    callback: function(val, index) {
                      return '';
                    },
                    color: 'red',
                  },
                },
              }
            }
          },
          tools: {
            data: {
              labels: ['VSCode', 'NPM', 'Postman', 'Github Copilot', 'Github Actions', 'Git', 'Linux', 'Sublime Text 3/4', 'Docker'],
              datasets: [
                {
                    label: 'Tools',
                    backgroundColor: '#a855f7',
                    data: [100, 100, 100, 100, 90, 90, 90, 80, 75],
                },
              ],
              options: {
                responsive: true,
                maintainAspectRatio: false,
                indexAxis: 'y',
                scales: {
                  x: {
                    ticks: {
                      callback: function(val, index) {
                        return '';
                      },
                      color: 'red',
                    },
                  },
                }
              }
            },
            options: {
              responsive: true,
              maintainAspectRatio: false,
              indexAxis: 'y',
              scales: {
                x: {
                  ticks: {
                    callback: function(val, index) {
                      return '';
                    },
                    color: 'red',
                  },
                },
              }
            }
          }
        }
      }
    }
  };
</script>

<style lang="scss" scoped>

  :root {
    --text-color: red;
  }
  section {
    flex-grow: 1;
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    gap: 2rem;

    justify-content: center;
  }

  .split {
    display: flex;
    gap: 3rem;

    .p-chart {
      min-height: 40vh;
    }
  }

  .p-chart {
    width: 100%;
    min-height: 30vh;
  }

  p.primary {
    font-size: 3rem;
    text-align: center;
  }

  @media screen and (max-width: 1300px){
    .split {
      flex-direction: column;
    }
  } 
</style>


