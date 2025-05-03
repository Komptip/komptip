<script setup>
import Carousel from 'primevue/carousel';
import Dialog from 'primevue/dialog';

import bbqimage1 from "/src/assets/portfolio/bbq/1.webp";
import bbqimage2 from "/src/assets/portfolio/bbq/2.webp";
import bbqimage3 from "/src/assets/portfolio/bbq/3.webp";

import eggbankimage1 from "/src/assets/portfolio/eggbank/1.webp";
import eggbankimage2 from "/src/assets/portfolio/eggbank/2.webp";
import eggbankimage3 from "/src/assets/portfolio/eggbank/3.webp";
import eggbankimage4 from "/src/assets/portfolio/eggbank/4.webp";
import eggbankimage5 from "/src/assets/portfolio/eggbank/5.webp";
import eggbankimage6 from "/src/assets/portfolio/eggbank/6.webp";
import eggbankimage7 from "/src/assets/portfolio/eggbank/7.webp";
import eggbankimage8 from "/src/assets/portfolio/eggbank/8.webp";

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

import pipleuimage1 from "/src/assets/portfolio/pipleu/1.webp";
import pipleuimage2 from "/src/assets/portfolio/pipleu/2.webp";
import pipleuimage3 from "/src/assets/portfolio/pipleu/3.webp";
import pipleuimage4 from "/src/assets/portfolio/pipleu/4.webp";
import pipleuimage5 from "/src/assets/portfolio/pipleu/5.webp";

import zernyatkoimage1 from "/src/assets/portfolio/zernyatko/1.webp";
import zernyatkoimage2 from "/src/assets/portfolio/zernyatko/2.webp";
import zernyatkoimage3 from "/src/assets/portfolio/zernyatko/3.webp";
import zernyatkoimage4 from "/src/assets/portfolio/zernyatko/4.webp";

import themyasoimage1 from "/src/assets/portfolio/themyaso/1.webp";
import themyasoimage2 from "/src/assets/portfolio/themyaso/2.webp";

import checkboximage1 from "/src/assets/portfolio/checkbox/1.webp";

import vchasnoimage1 from "/src/assets/portfolio/vchasno/1.webp";

import esputnikimage1 from "/src/assets/portfolio/esputnik/1.webp";

import payeerimage1 from "/src/assets/portfolio/payeer/1.webp";

import stipeimage1 from "/src/assets/portfolio/stripe/1.webp";

import hundredmsimage1 from "/src/assets/portfolio/100ms/1.webp";

import squareupimage1 from "/src/assets/portfolio/squareup/1.webp";

import newlabelimage1 from "/src/assets/portfolio/newlabel/1.webp";
import newlabelimage2 from "/src/assets/portfolio/newlabel/2.webp";

import coolhouseimage1 from "/src/assets/portfolio/coolhouse/1.webp";
import coolhouseimage2 from "/src/assets/portfolio/coolhouse/2.webp";
import coolhouseimage3 from "/src/assets/portfolio/coolhouse/3.webp";

import speechkaimage1 from "/src/assets/portfolio/speechka/1.webp";
import speechkaimage2 from "/src/assets/portfolio/speechka/2.webp";
import speechkaimage3 from "/src/assets/portfolio/speechka/3.webp";

import aptimage1 from "/src/assets/portfolio/apt/1.webp";
import aptimage2 from "/src/assets/portfolio/apt/2.webp";
import aptimage3 from "/src/assets/portfolio/apt/3.webp";

import reposyimage1 from "/src/assets/portfolio/reposy/1.webp";
import reposyimage2 from "/src/assets/portfolio/reposy/2.webp";
</script>

<template>
  <section id="portfolio" class="flex">
    <h2 class="text-center text-6xl">Examples of my work</h2>
    <template v-for="category in categories">
      <h3 class="text-4xl">{{ category.name }}</h3>  
      <div class="category flex gap-2 flex-wrap">
        <template v-for="item in category.items">
          <div class="item flex w-12rem h-12rem flex-column-reverse bg-contain bg-no-repeat cursor-pointer item p-1" :style="'background-image:url(' + item.preview + ')'" v-on:click="selected = item">
            <p class="text-center mb-4 text-lg font-bold">{{ item.name }}</p>
          </div>
        </template>
      </div>
    </template>
    <Dialog v-model:visible="selected" modal :header="selected?.name" :style="{ width: '85rem' }" :draggable="false">
      <template v-for="component in selected.components">
        <template v-if="component.type === 'text'">
          <p class="text-lg">{{ component.content }}</p>
        </template>
        <template v-else-if="component.type === 'image'">
          <img :src="component.content" alt="image" class="w-full p-2" />
        </template>
      </template>
    </Dialog>

  </section>
</template>
<script>
  export default {
    data() {
      Carousel.methods.onTouchMove = () => { };
      return {
        selected: null,
        categories: [
          {
            name: "Websites",
            items: [
            {
                name: "Egg Bank",
                preview: eggbankimage1,
                components: [
                  {
                    type: 'text',
                    content: 'Professional website for a medical agency specializing in ovum donation, based in Ukraine.'
                  },
                  {
                    type: 'image',
                    content: eggbankimage1
                  },
                  {
                    type: 'text',
                    content: 'Facilitates online ovum procurement with advanced donor filtering. Comprehensive donor profiles available.'
                  },
                  {
                    type: 'image',
                    content: eggbankimage8
                  },
                  {
                    type: 'image',
                    content: eggbankimage5
                  },
                  {
                    type: 'text',
                    content: 'Features user accounts with detailed order and profile management.'
                  },
                  {
                    type: 'image',
                    content: eggbankimage6
                  },
                  {
                    type: 'image',
                    content: eggbankimage7
                  },
                  {
                    type: 'image',
                    content: eggbankimage3
                  },
                  {
                    type: 'image',
                    content: eggbankimage4
                  },
                  {
                    type: 'image',
                    content: eggbankimage2
                  }
                ]
              },
              {
                name: "Tim's Barbecue",
                preview: bbqimage1,
                components: [
                  {
                    type: 'text',
                    content: 'Online ordering platform for Tim\'s Barbecue, a Philadelphia-based restaurant chain.'
                  },
                  {
                    type: 'image',
                    content: bbqimage1
                  },
                  {
                    type: 'text',
                    content: 'Features include table reservations, food ordering, tipping, and online payment via SquareUp API integration.'
                  },
                  {
                    type: 'image',
                    content: bbqimage2
                  },
                  {
                    type: 'image',
                    content: bbqimage3
                  }
                ]
              },
              {
                name: "Fort Wayne Ballet School",
                preview: balletimage1,
                components: [
                  {
                    type: 'text',
                    content: 'Website for ballet school, located in Fort Wayne, Indiana'
                  },
                  {
                    type: 'image',
                    content: balletimage1
                  },
                  {
                    type: 'image',
                    content: balletimage2
                  },
                  {
                    type: 'image',
                    content: balletimage3
                  },
                  {
                    type: 'image',
                    content: balletimage4
                  }
                ]
              },
              {
                name: "18 Wheeler Driving School",
                preview: drivingschoolimage1,
                components: [
                  {
                    type: 'text',
                    content: 'Online platform for 18 Wheels truck driving school. Offers driver\'s license practice tests in English, Ukrainian, and Russian.'
                  },
                  {
                    type: 'image',
                    content: drivingschoolimage1
                  },
                  {
                    type: 'image',
                    content: drivingschoolimage2
                  },
                  {
                    type: 'image',
                    content: drivingschoolimage3
                  },
                  {
                    type: 'image',
                    content: drivingschoolimage4
                  }
                ]
              },
              {
                name: "Buty Poruch",
                preview: butyporuchimage1,
                components: [
                  {
                    type: 'text',
                    content: 'Website for Buty Poruch, a Ukrainian non-profit organization dedicated to cancer awareness and support.'
                  },
                  {
                    type: 'image',
                    content: butyporuchimage1
                  },
                  {
                    type: 'text',
                    content: 'Comprehensive resource featuring articles, news, and cancer-related information.'
                  },
                  {
                    type: 'image',
                    content: butyporuchimage2
                  },
                  {
                    type: 'image',
                    content: butyporuchimage3
                  },
                  {
                    type: 'image',
                    content: butyporuchimage4
                  }
                ]
              },
              {
                name: "Hotels",
                preview: hotelsimage1,
                components: [
                  {
                    type: 'text',
                    content: 'Tenant tracking system for hotel pool lifeguards, accommodating multiple guests per tenant.'
                  },
                  {
                    type: 'image',
                    content: hotelsimage1
                  }
                ]
              },
              {
                name: "Pipl security systems",
                preview: pipleuimage1,
                components: [
                  {
                    type: 'text',
                    content: 'Pipl.eu: E-commerce platform for security systems in Czech Republic. Features comprehensive functionality including categorization, shopping cart, order history, and payment processing. Contributed to both front-end and back-end development during tenure at OwlWeb.'
                  },
                  {
                    type: 'image',
                    content: pipleuimage1
                  },
                  {
                    type: 'image',
                    content: pipleuimage2
                  },
                  {
                    type: 'image',
                    content: pipleuimage3
                  },
                  {
                    type: 'image',
                    content: pipleuimage4
                  },
                  {
                    type: 'image',
                    content: pipleuimage5
                  }
                ]
              },
              {
                name: "Zernyatko",
                preview: zernyatkoimage1,
                components: [
                  {
                    type: 'text',
                    content: 'Zernyatko: E-commerce platform for seeds and fertilizers. Contributed to front-end and back-end development at OwlWeb.'
                  },
                  {
                    type: 'image',
                    content: zernyatkoimage1
                  },
                  {
                    type: 'image',
                    content: zernyatkoimage2
                  },
                  {
                    type: 'image',
                    content: zernyatkoimage3
                  },
                  {
                    type: 'image',
                    content: zernyatkoimage4
                  }
                ]
              },
              {
                name: "New Label",
                preview: newlabelimage1,
                components: [
                  {
                    type: 'text',
                    content: 'New Label: Advertising agency website developed using Vite, Vue 3, SCSS, PrimeVue components, and PrimeFlex CSS framework.'
                  },
                  {
                    type: 'image',
                    content: newlabelimage1
                  },
                  {
                    type: 'image',
                    content: newlabelimage2
                  }
                ]
              }
            ]
          },
          {
            name: "Integrations",
            items: [
              {
                name: "Delivery cost calculator with Google Maps API",
                preview: themyasoimage1,
                components: [
                  {
                    type: 'text',
                    content: 'Google Maps API-powered delivery cost calculator for store-to-client goods delivery.'
                  },
                  {
                    type: 'image',
                    content: themyasoimage1
                  },
                  {
                    type: 'image',
                    content: themyasoimage2
                  }
                ] 
              },
              {
                name: "Cool House online kitchen configurator",
                preview: coolhouseimage1,
                components: [
                  {
                    type: 'text',
                    content: 'Online kitchen configurator for Cool House, enabling kitchen design and cost calculation. Developed with vanilla JS and jQuery for CMS compatibility.'
                  },
                  {
                    type: 'image',
                    content: coolhouseimage1
                  },
                  {
                    type: 'image',
                    content: coolhouseimage2
                  },
                  {
                    type: 'image',
                    content: coolhouseimage3
                  }
                ]
              },
              {
                name: "Checkbox integration",
                preview: checkboximage1,
                components: [
                  {
                    type: 'text',
                    content: 'Laravel integration of Checkbox for fiscalized invoice issuance, utilizing Checkbox REST API.'
                  },
                  {
                    type: 'image',
                    content: checkboximage1
                  }
                ]
              },
              {
                name: "Vchasno integration",
                preview: vchasnoimage1,
                components: [
                  {
                    type: 'text',
                    content: 'Integration of Vchasno for electronic document signing, implemented as a Laravel Service using Vchasno REST API.'
                  },
                  {
                    type: 'image',
                    content: vchasnoimage1
                  }
                ]
              },
              {
                name: 'eSputnik integration',
                preview: esputnikimage1,
                components: [
                  {
                    type: 'text',
                    content: 'eSputnik integration for SMS/email sending and client management, developed as a Laravel Service using eSputnik REST API.'
                  },
                  {
                    type: 'image',
                    content: esputnikimage1
                  }
                ]
              },
              {
                name: '100ms integration',
                preview: hundredmsimage1,
                components: [
                  {
                    type: 'text',
                    content: 'Integration of 100ms for video conferencing, developed as a Laravel Service using 100ms REST API.'
                  },
                  {
                    type: 'image',
                    content: hundredmsimage1
                  }
                ]
              },
              {
                name: 'Payeer integration',
                preview: payeerimage1,
                components: [
                  {
                    type: 'text',
                    content: 'Full integration of Payeer online payment processing service into an e-commerce platform using Payeer REST API.'
                  },
                  {
                    type: 'image',
                    content: payeerimage1
                  }
                ]
              },
              {
                name: 'Stripe integration',
                preview: stipeimage1,
                components: [
                  {
                    type: 'text',
                    content: 'Integration of Stripe online payment processing service.'
                  },
                  {
                    type: 'image',
                    content: stipeimage1
                  }
                ]
              },
              {
                name: 'SquareUp integration',
                preview: squareupimage1,
                components: [
                  {
                    type: 'text',
                    content: 'Integration of SquareUp online payment processing service.'
                  },
                  {
                    type: 'image',
                    content: squareupimage1
                  }
                ]
              }
            ]
          },
          {
            name: "Pet projects",
            items: [
              {
                name: "Reposy - AI Google Chrome extension",
                preview: reposyimage1,
                components: [
                  {
                    type: 'text',
                    content: 'Reposy is a Google Chrome extension for developers that integrates with Google Gemini 1.5 LLM. It allows loading of entire repositories from Github, Gitlab, or Bitbucket for content analysis. Built with Vue 3 and Primevue components, it\'s available on the Chrome Web Store.'
                  },
                  {
                    type: 'image',
                    content: reposyimage1
                  },
                  {
                    type: 'image',
                    content: reposyimage2
                  }
                ]
              },
              {
                name: "AI powered programming tool",
                preview: aptimage1,
                components: [
                  {
                    type: 'text',
                    content: 'An experimental project from spring 2024 aimed at automating software development. Utilizes Gemini 1.5 with a 1 million token context length for comprehensive code analysis. While the AI-generated code quality is currently insufficient for production use, the project demonstrates potential in AI-assisted development.'
                  },
                  {
                    type: 'image',
                    content: aptimage1
                  },
                  {
                    type: 'image',
                    content: aptimage2
                  },
                  {
                    type: 'image',
                    content: aptimage3
                  }
                ]
              },
              {
                name: "Reddit clone Speechka",
                preview: speechkaimage1,
                components: [
                  {
                    type: 'text',
                    content: 'A Reddit-inspired platform developed in late 2022. Features include post creation, commenting, and voting. While no longer active, the source code is available on GitHub, serving as a learning exercise in complex web application development.'
                  },
                  {
                    type: 'image',
                    content: speechkaimage1
                  },
                  {
                    type: 'image',
                    content: speechkaimage2
                  },
                  {
                    type: 'image',
                    content: speechkaimage3
                  }
                ]
              }
            ]
          }
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

  .item {
    background-color: rgba(0, 0, 0, 0.25);

    p {
      text-shadow: -1px -3px 20px rgb(0, 0, 0);
    }
    
    &:hover {
      background-color: rgba(0, 0, 0, 0.5);
    }
  }

  @media screen and (max-width: 1300px){
    .item {
      width: 100% !important;
      
      background-position: center;
      background-size: cover !important;

      margin-top: 1rem;
      margin-bottom: 1rem;

      p {
        background-color: rgba(0, 0, 0, 0.5);

        padding-bottom: 1rem;
        padding-top: 1rem;
      }
    }
  }
</style>


