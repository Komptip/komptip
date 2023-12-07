<script setup>
import Carousel from 'primevue/carousel';

import bbqimage1 from "/src/assets/portfolio/bbq/1.webp";
import bbqimage2 from "/src/assets/portfolio/bbq/2.webp";
import bbqimage3 from "/src/assets/portfolio/bbq/3.webp";

import eggbankimage1 from "/src/assets/portfolio/eggbank/1.webp";
import eggbankimage2 from "/src/assets/portfolio/eggbank/2.webp";
import eggbankimage3 from "/src/assets/portfolio/eggbank/3.webp";

import balletimage1 from "/src/assets/portfolio/ballet/1.webp";
import balletimage2 from "/src/assets/portfolio/ballet/2.webp";
import balletimage3 from "/src/assets/portfolio/ballet/3.webp";
import balletimage4 from "/src/assets/portfolio/ballet/4.webp";

import drivingschoolimage1 from "/src/assets/portfolio/18wheels/1.webp";
import drivingschoolimage2 from "/src/assets/portfolio/18wheels/2.webp";
import drivingschoolimage3 from "/src/assets/portfolio/18wheels/3.webp";
import drivingschoolimage4 from "/src/assets/portfolio/18wheels/4.webp";

import butyporuchimage1 from "/src/assets/portfolio/butyporuch/1.webp";
import butyporuchimage2 from "/src/assets/portfolio/butyporuch/2.webp";
import butyporuchimage3 from "/src/assets/portfolio/butyporuch/3.webp";
import butyporuchimage4 from "/src/assets/portfolio/butyporuch/4.webp";

import hotelsimage1 from "/src/assets/portfolio/hotels/1.webp";
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
      Carousel.methods.onTouchMove = () => { };
      return {
        items: [
          [
            {
              title: "Tim's Barbecue",
              image: bbqimage2,
              description: 'Website for Philadelphian barbecue restaurant chain Tim\'s Barbecue',
              tags: ['Entirely made', 'Technical support']
            },
            {
              title: "Tim's Barbecue",
              image: bbqimage1,
              description: 'The website allows you to customise and select different chain restaurants, menus, categories and dishes. Payment is done online using SquareUp API'
            },
            {
              title: "Tim's Barbecue",
              image: bbqimage3,
              description: 'From the administrator\s side there is the possibility of convenient management of customers and orders, receiving notifications, including notification of new orders, stock quantities and others'
            },
          ],
          [
            {
              title: "Adonis Eggbank",
              image: eggbankimage1,
              description: 'A website for purchasing oocytes from donors of Adonis Eggbank',
              tags: ['Partially made', 'Technical support']
            },
            {
              title: "Adonis Eggbank",
              image: eggbankimage2,
              description: 'The website is multi-lingual, has a personal account allowing you to view donors, add them to your favourites, buy and compare them'
            },
            {
              title: "Adonis Eggbank",
              image: eggbankimage3,
              description: 'The site contains lots of customisable information about the donor, including photos, signature, family tree and more'
            }
          ],
          [
            {
              title: "Fort wayne ballet",
              image: balletimage1,
              description: 'Web site for Fort Wayne Ballet\'s ballet school',
              tags: ['Technical support']
            },
            {
              title: "Fort wayne ballet",
              image: balletimage2,
              description: '',
              tags: []
            },
            {
              title: "Fort wayne ballet",
              image: balletimage3,
              description: '',
              tags: []
            },
            {
              title: "Fort wayne ballet",
              image: balletimage4,
              description: '',
              tags: []
            }
          ],
          [
            {
              title: "CDL testing portal for 18 Wheeler",
              image: drivingschoolimage1,
              description: 'An online portal to take driving tests for 18 Wheeler Driving School',
              tags: ['Entirely made']
            },
            {
              title: "CDL testing portal for 18 Wheeler",
              image: drivingschoolimage2,
              description: '',
              tags: []
            },
            {
              title: "CDL testing portal for 18 Wheeler",
              image: drivingschoolimage3,
              description: '',
              tags: []
            },
            {
              title: "CDL testing portal for 18 Wheeler",
              image: drivingschoolimage4,
              description: '',
              tags: []
            },
          ],
          [
            {
              title: "Buty Poruch",
              image: butyporuchimage1,
              description: 'Ukrainian portal to help cancer patients',
              tags: ['Technical support']
            },
            {
              title: "Buty Poruch",
              image: butyporuchimage2,
              description: 'The website contains many useful articles on a variety of topics',
              tags: []
            },
            {
              title: "Buty Poruch",
              image: butyporuchimage3,
              description: '',
              tags: []
            },
            {
              title: "Buty Poruch",
              image: butyporuchimage4,
              description: '',
              tags: []
            }
          ],
          [
            {
              title: "Hotel tenants tracking system",
              image: hotelsimage1,
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

  @media (max-width: 670px) {
    :deep(.p-carousel-prev), :deep(.p-carousel-next){
      display: none;
    }
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
      
    @media (max-width: 670px) {
      & {
        height: 60vh;
      }
    }

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

        
        @media (max-width: 670px) {
          & {
            font-size: 1.5rem;
          }
        }
      }

      .description {
        font-size: 1.2rem;

        
        @media (max-width: 670px) {
          & {
            font-size: 0.9rem;
          }
        }
      }
      
      .tags {
        margin-top: 1.4rem;
        margin-bottom: 1rem;

        font-size: 1.3rem;
        display: flex;
        gap: 4rem;

        
        @media (max-width: 670px) {
          & {
            font-size: 1.1rem;
          }
        }
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


