<script setup>
import DocumentationIcon from './icons/IconDocumentation.vue'
import ToolingIcon from './icons/IconTooling.vue'
import EcosystemIcon from './icons/IconEcosystem.vue'
import CommunityIcon from './icons/IconCommunity.vue'
import SupportIcon from './icons/IconSupport.vue'
import Carousel from 'primevue/carousel';
</script>

<template>
  <section id="portfolio">
    <p class="primary">I made...</p>
    <template v-for="itemList, index in items">
      <Carousel :ref="'portfolio-item#' + index" :value="itemList" :numVisible="1" :numScroll="1" :pt="{previousButtonIcon: {'width': '1.5rem', 'height': '1.5rem'}, nextButtonIcon: {'width': '1.5rem', 'height': '1.5rem'}}">
        <template #item="item">
          <div class="image" :style="{'background-image': `url(${item.data.image})`}">
            <div class="transition"></div>
            <div class="card">
              <p class="title">{{ item.data.title }}</p>
              <p class="description">
                {{ item.data.description }}
              </p>
              <ul class="tags">
                <li v-for="tag in item.data.tags">{{ tag }}</li>
              </ul>
              <p class="learn-more" v-if="itemList.length - 1 > item.index" v-on:click="$refs['portfolio-item#' + index][0].navForward({})">Learn more</p>
            </div>
          </div>
        </template>
      </Carousel>
    </template>
  </section>
</template>
<script>
  export default {
    data() {
      return {
        items: [
          [
            {
              title: "Tim's Barbecue",
              image: "/src/assets/portfolio/bbq/2.webp",
              description: 'Website for Philadelphian barbecue restaurant chain Tim\'s Barbecue',
              tags: ['Entirely made', 'Technical support']
            },
            {
              title: "Tim's Barbecue",
              image: "/src/assets/portfolio/bbq/1.webp",
              description: 'The website allows you to customise and select different chain restaurants, menus, categories and dishes. Payment is done online using SquareUp API'
            },
            {
              title: "Tim's Barbecue",
              image: "/src/assets/portfolio/bbq/3.webp",
              description: 'From the administrator\s side there is the possibility of convenient management of customers and orders, receiving notifications, including notification of new orders, stock quantities and others'
            },
          ],
          [
            {
              title: "Adonis Eggbank",
              image: "/src/assets/portfolio/eggbank/1.webp",
              description: 'A website for purchasing oocytes from donors of Adonis Eggbank',
              tags: ['Partially made', 'Technical support']
            },
            {
              title: "Adonis Eggbank",
              image: "/src/assets/portfolio/eggbank/2.webp",
              description: 'The website is multi-lingual, has a personal account allowing you to view donors, add them to your favourites, buy and compare them'
            },
            {
              title: "Adonis Eggbank",
              image: "/src/assets/portfolio/eggbank/2.webp",
              description: 'The site contains lots of customisable information about the donor, including photos, signature, family tree and more'
            }
          ],
          [
            {
              title: "Fort wayne ballet",
              image: "/src/assets/portfolio/ballet/1.webp",
              description: 'Web site for Fort Wayne Ballet\'s ballet school',
              tags: ['Technical support']
            },
            {
              title: "Fort wayne ballet",
              image: "/src/assets/portfolio/ballet/2.webp",
              description: '',
              tags: []
            },
            {
              title: "Fort wayne ballet",
              image: "/src/assets/portfolio/ballet/3.webp",
              description: '',
              tags: []
            },
            {
              title: "Fort wayne ballet",
              image: "/src/assets/portfolio/ballet/4.webp",
              description: '',
              tags: []
            }
          ],
          [
            {
              title: "CDL testing portal for 18 Wheeler",
              image: "/src/assets/portfolio/18wheels/1.webp",
              description: 'An online portal to take driving tests for 18 Wheeler Driving School',
              tags: ['Entirely made']
            },
            {
              title: "CDL testing portal for 18 Wheeler",
              image: "/src/assets/portfolio/18wheels/2.webp",
              description: '',
              tags: []
            },
            {
              title: "CDL testing portal for 18 Wheeler",
              image: "/src/assets/portfolio/18wheels/3.webp",
              description: '',
              tags: []
            },
            {
              title: "CDL testing portal for 18 Wheeler",
              image: "/src/assets/portfolio/18wheels/4.webp",
              description: '',
              tags: []
            },
          ],
          [
            {
              title: "Buty Poruch",
              image: "/src/assets/portfolio/butyporuch/1.webp",
              description: 'Ukrainian portal to help cancer patients',
              tags: ['Technical support']
            },
            {
              title: "Buty Poruch",
              image: "/src/assets/portfolio/butyporuch/2.webp",
              description: 'The website contains many useful articles on a variety of topics',
              tags: []
            },
            {
              title: "Buty Poruch",
              image: "/src/assets/portfolio/butyporuch/3.webp",
              description: '',
              tags: []
            },
            {
              title: "Buty Poruch",
              image: "/src/assets/portfolio/butyporuch/4.webp",
              description: '',
              tags: []
            }
          ],
          [
            {
              title: "Hotel tenants tracking system",
              image: "/src/assets/portfolio/hotels/1.webp",
              description: 'A system for tracking tenants and their guests in a hotel chain',
              tags: ['Entirely made', 'Technical support']
            }
          ]
        ]
      }
    }
  };
</script>

<style lang="scss" scoped>
  section {
    flex-grow: 1;
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    gap: 2rem;

    justify-content: center;
  }

  .p-carousel {
    max-width: 100%;
  }

  :deep(.p-carousel-prev svg path), :deep(.p-carousel-next svg path){
    fill: var(--color-text);
  }

  p.primary {
    font-size: 3rem;
    text-align: center;
  }
  
  .image {
    height: 70vh;
    cursor: pointer;

    background-position: center;
    background-size: 107%;
    background-repeat: no-repeat;

    border-top-left-radius: 1rem;
    border-top-right-radius: 1rem;
    position: relative;

    margin-left: 1rem;
    margin-right: 1rem;

    display: flex;
    flex-direction: column;

    .transition {
      position: absolute;
      width: 100%;
      height: 80%;

      bottom: 0px;

      background-image: linear-gradient(to bottom, rgba(0,0,0,0) 0%, rgba(36,42,56,0.4290091036414566) 16%, var(--color-background) 90%);
    }

    .card {
      margin-top: auto;

      display: flex;
      flex-direction: column;

      padding: 1.5rem;


      z-index: 1;

      .title {
        font-size: 2.5rem;
      }

      .description {
        font-size: 1.2rem;
      }
      
      .tags {
        margin-top: 1.4rem;
        margin-bottom: 1rem;

        font-size: 1.3rem;
        display: flex;
        gap: 4rem;
      }

      .learn-more {
        margin-top: 0.2rem;
        font-size: 2rem;
        color: var(--vt-c-soft-white);

        &::after {
          content: "→";
          padding-left: 10px;
          transition: padding-left 0.2s;
        }
      }
    }

    transition: background-size 0.5s;

    &:hover {
      background-size: 112%;
      
      transition: background-size 0.5s;

      .learn-more {
        color: white;
        user-select: none;

        &::after {
          padding-left: 14px;
          transition: padding-left 0.2s;
        }
      }
    }
  }

</style>


