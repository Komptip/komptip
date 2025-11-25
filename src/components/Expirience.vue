<script setup>
import Timeline from 'primevue/timeline';
import Card from 'primevue/card';
import Button from 'primevue/button';
import 'primevue/resources/themes/lara-dark-indigo/theme.css'
import '/node_modules/primeflex/primeflex.css'

import freelancephoto from '/src/assets/freelancehunt-photo.webp';
import zentixlogo from '/src/assets/zentix-logo.webp';
import owlweblogo from '/src/assets/owlweb-logo.webp';
import outsoftlogo from '/src/assets/outsoft-logo.webp';
import dilizylogo from '/src/assets/dilizy-logo.webp';

</script>

<template>
  <section id="expirience">
    <p class="primary">My expirience</p>
    <Timeline :value="events" align="alternate" class="customized-timeline">
      <template #marker="slotProps">
        <span class="flex w-2rem h-2rem align-items-center justify-content-center text-white border-circle z-1 shadow-1"
          :style="{ backgroundColor: slotProps.item.color }">
          <i :class="slotProps.item.icon"></i>
        </span>
      </template>
      <template #content="slotProps">
        <Card class="mt-3">
          <template #title>
            {{ slotProps.item.status }}
          </template>
          <template #subtitle>
            {{ slotProps.item.date }}
          </template>
          <template #content>
            <img v-if="slotProps.item.images" v-for="image in slotProps.item.images" :src="image.src" :alt="image.alt"
              class="w-10rem border-circle" />
            <p>
              {{ slotProps.item.text }}
            </p>
            <div class="mt-3">
              <a v-for="button in slotProps.item.buttons" :href="button.link" target="_blank">
                <Button :label="button.text" :key="button.text" :class="button.classes"></Button>
              </a>
            </div>
          </template>
        </Card>
      </template>
    </Timeline>
  </section>
</template>
<script>
  export default {
    data() {
      return {
        events: [
          {
            status: 'Freelance', date: 'September 2019 - January 2022',
            icon: 'pi pi-map',
            color: 'orange',
            images: [
              { src: freelancephoto, alt: 'Freelancehunt' }
            ],
            text: 'Over 3 years of freelance experience with 40+ successful projects, including large-scale e-commerce platforms, document management systems, and complex third-party integrations (e.g., payment gateways, 1C, and government services)',
            buttons: [
              { text: 'Profile on freelancehunt', link: 'https://freelancehunt.com/en/freelancer/komptip.html#reviews', classes: 'text-sm text-white bg-orange-500 border-yellow-800' }
            ]
          },
          {
            status: 'Zenetix Digital Production',
            date: 'February 2022 - March 2023',
            icon: 'pi pi-briefcase',
            color: '#3f51b5',
            images: [
              { src: zentixlogo, alt: 'Zenetix' }
            ],
            text: 'First full-time experience working collaboratively on complex projects. Primarily used Laravel and Vue.js to develop new applications and maintain existing ones, gaining hands-on experience across the full development lifecycle',
            buttons: [
              { text: 'Zenetix website', link: 'https://zenetix.com.ua/', classes: 'text-sm text-white bg-indigo-500 border-indigo-800' }
            ]
          },
          {
            status: 'Back-end Web Developer at Owlweb',
            date: 'April 2023 - April 2024',
            icon: 'pi pi-wrench',
            color: '#e677b9',
            images: [
              { src: owlweblogo, alt: 'OwlWeb' }
            ],
            text: 'Focused primarily on back-end development, with occasional front-end tasks using React, Vue, and jQuery. Worked on both internal tools and client projects, including e-commerce sites such as d2interier.com, pipl.eu, and zernyatko.in.ua. Participated in complex third-party integrations, including services like Vchasno (e-signatures) and Chekbox (electronic document management)',
            buttons: [
              { text: 'OwlWeb website', link: 'https://owlweb.com.ua/en', classes: 'text-sm text-white bg-pink-500 border-pink-800' }
            ]
          },
          {
            status: 'Web Developer at Outsoft',
            date: 'May 2024 - June 2025',
            icon: 'pi pi-briefcase',
            color: '#3f51b5',
            images: [
              { src: outsoftlogo, alt: 'Outsoft' }
            ],
            text: 'Provided technical support for a major e-commerce platform, focusing on bug fixes, performance optimization, and feature development. Simultaneously served as the lead developer on a new internal project',
            buttons: [
              { text: 'Outsoft website', link: 'https://outsoft.com/', classes: 'text-sm text-white bg-indigo-500 border-indigo-800' }
            ]
          },
          {
            status: 'Dilizy',
            date: 'July 2025 - December 2025',
            icon: 'pi pi-briefcase',
            color: '#9C27B0',
            images: [
              { src: dilizylogo, alt: 'Dilizy' }
            ],
            text: 'Maintained and improved a large ecosystem consisting of several major, tightly interconnected Laravel monoliths that regularly exchanged data with each other',
            buttons: [
              { text: 'Dilizy website', link: 'https://dilizy.ai/', classes: 'text-sm text-black bg-yellow-400 border-yellow-800' }
            ]
          }
        ].reverse()
      }
    }
  };
</script>

<style>
@media screen and (max-width: 1300px) {
  .p-timeline-event-opposite {
    display: none;
  }

  .p-timeline-vertical.p-timeline-alternate .p-timeline-event:nth-child(even) {
    flex-direction: row;
  }
}
</style>

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

@media screen and (max-width: 1300px) {
  .split {
    flex-direction: column;
  }
}
</style>
