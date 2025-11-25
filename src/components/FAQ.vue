<script setup>
import Accordion from 'primevue/accordion';
import AccordionTab from 'primevue/accordiontab';
import 'primevue/resources/themes/lara-dark-indigo/theme.css'

</script>

<template>
  <section id="faq">
    <p class="primary">FAQ</p>
    <Accordion :activeIndex="0">
        <AccordionTab header="Are you open to work? 🕐">
            <p class="m-0">
                <span class="font-bold underline">Yes</span>, recently i has been layed off from Dilizy due to organizational reasons. Currently i am focused on a few pet projects im working on. But <span class="font-bold underline">im fully open for new opportunities including full-time job.</span>
            </p>
        </AccordionTab>
        <AccordionTab header="What is your primary stack? 🪚🛠️">
            <p class="m-0">
              Mainly <span class="font-bold underline">Laravel with its ecosystem</span>, but i also have a lot of experience with different CMS such as <span class="font-bold underline">Wordpress, Opencart, Netcat</span>, etc. (View my <a href="#stack">stack</a>)
            </p>
        </AccordionTab>
        <AccordionTab header="What role are you looking for? 🫂">
            <p class="m-0">
              My main focus for last few years was <span class="font-bold underline">back-end development</span>, but i also have a <span class="font-bold underline">ton of experience with front-end development</span>.
              I also <span class="font-bold underline">would be intrested in PM/Team Leading roles</span>, i have a strong experience in team management and leading, plus bachelor's degree in management.
            </p>
        </AccordionTab>
        <AccordionTab header="What is your availability? 🕰️">
            <p class="m-0">
              I am <span class="font-bold underline">available for remote work</span> and <span class="font-bold underline"> relocation</span> if needed. Currently i am based in <span class="font-bold underline">Lublin, Poland</span>.
            </p>
        </AccordionTab>
        <AccordionTab header="What languages do you speak? 🗣️">
            <p class="m-0">
              I speak <span class="font-bold underline">English</span> and <span class="font-bold underline">Russian</span>, <span class="font-bold underline">Ukrainian</span> fluently. My level of <span class="font-bold underline">Polish</span> is intermediate.
            </p>
        </AccordionTab>
        <AccordionTab header="Have you worked in teams? 🧑‍🤝‍🧑">
          <p class="m-0">
              Yes, I’ve worked in <span class="font-bold underline">cross-functional teams</span> of various sizes using <span class="font-bold underline">Agile/Scrum</span> methodologies. I’m also comfortable mentoring junior devs and taking ownership of key features.
          </p>
      </AccordionTab>
      <AccordionTab header="Do you have any open-source or side projects? 🌱">
          <p class="m-0">
              Yes, I’m currently working on a few <span class="font-bold underline">pet projects</span>, including a browser extension and several Laravel-based apps. You can find them on my <a href="https://github.com/Komptip" target="_blank">GitHub</a>.
          </p>
      </AccordionTab>
      <AccordionTab header="How good you are at stress management? 🤯">
          <p class="m-0">
            I was born in <a target="_blank" href="https://deepstatemap.live/#dl!coords!50.9056308936385,34.80606079101563">Sumy, Ukraine</a> so i have a lot of expirience with stress management 😅
          </p>
      </AccordionTab>
      <AccordionTab header="What bike do you ride? 🚲">
          <p class="m-0">
            Its <span class="font-bold underline">Rockrider ST 540</span> 😁              
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


