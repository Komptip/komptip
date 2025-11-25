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

import checkboximage1 from "/src/assets/portfolio/checkbox/1.webp";

import vchasnoimage1 from "/src/assets/portfolio/vchasno/1.webp";

import esputnikimage1 from "/src/assets/portfolio/esputnik/1.webp";

import payeerimage1 from "/src/assets/portfolio/payeer/1.webp";

import stipeimage1 from "/src/assets/portfolio/stripe/1.webp";

import hundredmsimage1 from "/src/assets/portfolio/100ms/1.webp";

import squareupimage1 from "/src/assets/portfolio/squareup/1.webp";

import otomotoimage1 from "/src/assets/portfolio/otomoto/1.webp";

import n8nimage1 from "/src/assets/portfolio/n8n/1.webp";

import makecomimage1 from "/src/assets/portfolio/makecom/1.webp";

import newlabelimage1 from "/src/assets/portfolio/newlabel/1.webp";
import newlabelimage2 from "/src/assets/portfolio/newlabel/2.webp";

import aptimage1 from "/src/assets/portfolio/apt/1.webp";
import aptimage2 from "/src/assets/portfolio/apt/2.webp";
import aptimage3 from "/src/assets/portfolio/apt/3.webp";

import reposyimage1 from "/src/assets/portfolio/reposy/1.webp";
import reposyimage2 from "/src/assets/portfolio/reposy/2.webp";

import tiktokimage1 from "/src/assets/portfolio/php-tiktok-sdk/1.webp";
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
            name: "Some of websites i have built",
            items: [
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
                name: "Otomoto integration",
                preview: otomotoimage1,
                components: [
                  {
                    type: 'text',
                    content: 'Integration with Otomoto, Poland\'s largest automotive marketplace. Developed automated vehicle listing synchronization system that manages inventory updates, pricing changes, and vehicle specifications across the platform using Otomoto API.'
                  },
                  {
                    type: 'image',
                    content: otomotoimage1
                  }
                ]
              },
              {
                name: "n8n workflow automation",
                preview: n8nimage1,
                components: [
                  {
                    type: 'text',
                    content: 'Implementation of n8n workflow automation platform for business process automation. Created custom workflows integrating multiple services, APIs, and databases to streamline operations and reduce manual tasks.'
                  },
                  {
                    type: 'image',
                    content: n8nimage1
                  }
                ]
              },
              {
                name: "Make.com automation",
                preview: makecomimage1,
                components: [
                  {
                    type: 'text',
                    content: 'Integration and automation solutions using Make.com (formerly Integromat). Designed and implemented complex automation scenarios connecting various applications and services to optimize business workflows.'
                  },
                  {
                    type: 'image',
                    content: makecomimage1
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
                name: "PHP TikTok SDK",
                preview: tiktokimage1,
                components: [
                  {
                    type: 'text',
                    content: 'A PHP SDK for the TikTok API, providing a simple and easy-to-use interface for accessing TikTok\'s API. Built with Guzzle, it\'s available on GitHub.'
                  },
                  {
                    type: 'image',
                    content: tiktokimage1
                  }
                ]
              },
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
              }
            ]
          }
        ].reverse()
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


