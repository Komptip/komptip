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
                My primary stack is Laravel and Vue 3. Also i had expirience with Vue 2, Nuxt and jQuery if we talk about Javscript, PHP - Symfony, CSS - SCSS and SASS. And numerous CMS systems, such as Wordpress, Opencard (2, 3), Netcat, Shopify, Tilda
                <br/><br/>
                For a few projects i needed to create real-time 3D scenes renderers, so i know webGL and THREE.js.<br/>
                Also i know Python and often use it for my side projects
            </p>
        </AccordionTab>
        <AccordionTab header="What is your work expirience?">
            <p class="m-0">
                More than 3 years. I started my project in web development in the fall of 2019
            </p>
        </AccordionTab>
        <AccordionTab header="Where did you work before?">
            <p class="m-0">
                Primarely on Freelance. For example <a href="https://freelancehunt.com/freelancer/komptip.html" target="_blank">this</a> is my profile on popular ukrainian freelance platform.
                But also for a some period of time i has been worked in teams, such as <a href="https://zenetix.com.ua/" target="_blank">Zentix</a>. Also in summer of 2023 i managed own web development team called <a href="https://instagram.com/webwi.zard.pl?igshid=NGVhN2U2NjQ0Yg==" target="_blank">Web Wizards</a>
            </p>
        </AccordionTab>
        <AccordionTab header="Can you show examples of your code?">
            <p class="m-0">
                Sure. On my Github you can <a href="https://github.com/Komptip/komptip" target="_blank">find source code of this website</a>
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


