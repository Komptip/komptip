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
    <h2 class="text-center text-6xl">I made...</h2>
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
                    content: 'Website for egg donation agency Egg Bank. The agency is located in Ukraine'
                  },
                  {
                    type: 'image',
                    content: eggbankimage1
                  },
                  {
                    type: 'text',
                    content: 'Gives ability to buy a donor eggs online. Donors can be filtered by many different valuees. Each donor has a detailed profile with all the necessary information, each profile is deeply customizeble'
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
                    content: 'Has a user profile with all the necessary information about the account and the orders'
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
                name: "BBQ",
                preview: bbqimage1,
                components: [
                  {
                    type: 'text',
                    content: 'Website for food ordering Tim\'s Barbecue. Philadelphia barbecue restaurant chain'
                  },
                  {
                    type: 'image',
                    content: bbqimage1
                  },
                  {
                    type: 'text',
                    content: 'Has ability to book a table, order food, leave a tip and pay for the order online. For payment SquareUp API is used'
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
                name: "Ballet",
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
                name: "18 Wheels",
                preview: drivingschoolimage1,
                components: [
                  {
                    type: 'text',
                    content: 'Website for students of truck driving school 18 Wheels. Gives ability for students of driving school to try a different tests for a driver\'s license online. Tests can be taken in different 3 different languages: English, Ukrainian and Russian'
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
                    content: 'Website for shoe store Buty Poruch, ukrainian non-profit organization that helps people fight cancer'
                  },
                  {
                    type: 'image',
                    content: butyporuchimage1
                  },
                  {
                    type: 'text',
                    content: 'Website contains a bunch of different articles, news and information related to cancer'
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
                    content: 'System of tenants tracking for hotel pool lifeguards. Each tenant can have a multiple guests'
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
                    content: 'Pipl.eu. Security systems shop in Czech Republic. Has a complex functionality categories, cart, order history, payment. I was involved in the development of the front-end and back-end parts of the project during my work at OwlWeb'
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
                    content: 'Zernyatko. Online store of seeds and fertilizers. I was involved in the development of the front-end and back-end parts of the project during my work at OwlWeb'
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
                    content: 'New Label. Advertising agency website. Fully created by me. Powered by Vite, Vue 3 and SCSS. Uses PrimeVue components and PrimeFlex css framework'
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
                    content: 'Delivery cost calculator powered by Google Maps API. The calculator is used to calculate the cost of delivery of goods from the store to clients'
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
                    content: 'Online kitchen configurator for Cool House. The configurator is used to configure the kitchen and calculate the cost of the kitchen. Made with vanilla JS and jQuery due to website CMS'
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
                    content: 'Fully made by me. Laravel integration of Checkbox - Service for issuance of fiscalized invoice. Uses Checkbox REST API. Made as Laravel Service'
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
                    content: 'Integration of Vchasno - Service for signing documents using electronic signature. Uses Vchasno REST API. Made as Laravel Service'
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
                    content: 'Integration of eSputnik - Service for sms and email sending, clients managment. Uses eSputnik REST API. Made as Laravel Service'
                  },
                  {
                    type: 'image',
                    content: esputnikimage1
                  }
                ]
              },
              {
                name: 'Payeer integration',
                preview: payeerimage1,
                components: [
                  {
                    type: 'text',
                    content: 'Integration of Payeer - Service for online payment processing. Uses Payeer REST API. Fully integrated into the online store'
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
                    content: 'Integration of Stripe - Service for online payment processing'
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
                    content: 'Integration of SquareUp - Service for online payment processing'
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
                    content: 'Reposy is my own google chrome extension for developers, its gives you ability to load any entire Github, Gitlab or Bitbucket repository to Google Gemini 1.5 LLM model and ask any questions about its content. Extension build with Vue 3 and Primevue components. Currently is not available publicly because im still in process of google chrome store verification'
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
                    content: 'My small project developed in spring of 2024 in attempt to automate the process of software development. Uses Gemini 1.5 with context length of 1 million tokens, which theoretically is enough to read and store in memory the entire code for large project. Script calls Gemini Python API and gives it ability to get list of all project files, read and edit each file of a project. Unfortunately, code generated by AI is not good enough, so tool cant be used to develop real projects. Code is available on my GitHub'
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
                    content: 'Website pretty similar to Reddit. Users can create posts, comment, upvote and downvote posts. Each post may have unlimited amount of blocks with different type of content. Created and existed in september-november 2022, currently not available. Source code is available on my GitHub, but code is very dirty due to the lack of experience in the development of such projects'
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


