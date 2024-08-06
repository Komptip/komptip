<script setup>
import Chart from 'primevue/chart';
import Timeline from 'primevue/timeline';
import Card from 'primevue/card';
import Button from 'primevue/button';
import 'primevue/resources/themes/lara-dark-indigo/theme.css'
import '/node_modules/primeflex/primeflex.css'

</script>

<template>
  <section id="expirience">
    <p class="primary">My expirience</p>
    <Timeline :value="events" align="alternate" class="customized-timeline">
        <template #marker="slotProps">
            <span class="flex w-2rem h-2rem align-items-center justify-content-center text-white border-circle z-1 shadow-1" :style="{ backgroundColor: slotProps.item.color }">
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
                    <img v-if="slotProps.item.images" v-for="image in slotProps.item.images" :src="image.src" :alt="image.alt" class="w-10rem border-circle" />
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
            status: 'Freelance', date: 'September 2019 - October 2022', 
            icon: 'pi pi-map', 
            color: 'orange',
            images: [
              { src: '/freelancehunt-photo.webp', alt: 'Freelancehunt' }
            ],
            text: 'I worked as a freelancer for over 3 years, completing more than 40 successful projects, including large-scale online stores, document management systems, and multiple integrations with third-party services (payment gateways, 1C, government services)',
            buttons: [
              { text: 'Profile on freelancehunt', link: 'https://freelancehunt.com/freelancer/komptip.html#reviews', classes: 'text-sm text-white bg-orange-500 border-yellow-800'}
            ]
            },
            { 
            status: 'Zenetix Digital Production',
            date: 'January 2022 - August 2023',
            icon: 'pi pi-briefcase',
            color: '#3f51b5',
            images: [
              { src: '/zentix-logo.webp', alt: 'Zenetix' }
            ],
            text: 'My first full-time experience working in a team on complex projects. My main tech stack was Laravel + Vue. I was involved in both developing new projects and maintaining existing ones.',
            buttons: [
              { text: 'Zenetix website', link: 'https://zenetix.com.ua/', classes: 'text-sm text-white bg-indigo-500 border-indigo-800'}
            ]
            },
            {
            status: 'Head of Own Web Development Team',
            date: 'April - July 2023',
            icon: 'pi pi-users',
            color: '#673AB7',
            images: [
              { src: '/webwizards-logo.webp', alt: 'WebWizards' }
            ],
            text: 'My first attempt at organizing my own web studio. Our team size reached 6 people at its peak. 4 programmers (including myself as the team leader) and 2 people responsible for finding clients, one for advertising, and another one for SMM.',
            buttons: [
              { text: 'Website (Not available)', link: 'https://webwizards.studio/', classes: 'text-sm text-white bg-gray-500 border-gray-800'},
              { text: 'Telegram channel', link: 'https://t.me/webwi_zards', classes: 'text-sm text-white bg-blue-500 border-blue-800'}
            ]
            },
            {
            status: 'Back-end Web Developer at Owlweb',
            date: 'January - July 2024',
            icon: 'pi pi-wrench',
            color: '#e677b9',
            images: [
              { src: '/owlweb-logo.webp', alt: 'OwlWeb' }
            ],
            text: 'Full-time work in web development. My main responsibility was back-end development, but I also worked on small front-end enhancements using React, Vue, and jQuery at different times. I worked on both internal and external projects, including online stores like d2interier.com, pipl.eu, zernyatko.in.ua, and others. I was involved in complex integrations with third-party services, such as the electronic signature service Vchasno and the electronic document management system Chekbox.',
            buttons: [
              { text: 'OwlWeb website', link: 'https://owlweb.com.ua/en', classes: 'text-sm text-white bg-pink-500 border-pink-800'}
            ]
            },
            {
            status: 'Co-founder of NewLabel',
            date: 'October 2023 - July 2024',
            icon: 'pi pi-globe',
            color: '#000',
            images: [
              { src: '/newlabel-logo.webp', alt: 'NewLabel' }
            ],
            text: 'Co-founder of an advertising agency in Lublin called NewLabel, which also specializes in website development. I play a managerial role, overseeing the entire development process.',
            buttons: [
              { text: 'NewLabel website', link: 'https://newlabel.pl/', classes: 'text-sm text-white bg-black-alpha-90 border-black-alpha-90'}
            ]
            }
        ]
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


