<script setup>
import Accordion from 'primevue/accordion';
import AccordionTab from 'primevue/accordiontab';
import 'primevue/resources/themes/lara-dark-indigo/theme.css'

</script>

<template>
  <section id="faq">
    <p class="primary">FAQ</p>
    <Accordion :activeIndex="0">
        <AccordionTab header="What is your stack?">
            <p class="m-0">
                My primary stack is Laravel and Vue 3. Also i had expirience with Vue 2, Nuxt, React and jQuery for Javascript part. PHP - Symfony, CSS - SCSS and SASS. While i was on freelance i had expirience with numerous CMS systems, such as Wordpress, Opencard (2, 3), Netcat, Shopify, Tilda
                <br/><br/>
                Some of projects i worked on required to create a 3D renderers, so i had expirience with webGL and THREE.js.<br/>
                Also i know Python and often use it for my side projects
            </p>
        </AccordionTab>
        <AccordionTab header="Can you show examples of your code?">
            <p class="m-0">
                Sure. On my Github you can <a href="https://github.com/Komptip/komptip" target="_blank">find source code of this website and some other software developed by me</a>
            </p>
        </AccordionTab>
    </Accordion>
  </section>
</template>
<script>
  export default {
    data() {
      return {

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

    align-items: center;
    justify-content: center;
  }

  p.primary {
      font-size: 3rem;
  }

  .p-accordion {
    width: 100%;
  }

  :deep(.p-accordion-header-text) {
    color: var(--color-text);
    margin-left: 1rem;
  }

  :deep(.p-accordion-toggle-icon path){
    fill: var(--color-text);
  }

  a {
    color: #818cf8;
  }
</style>


