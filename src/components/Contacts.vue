<script setup>
import DocumentationIcon from './icons/IconDocumentation.vue'
import ToolingIcon from './icons/IconTooling.vue'
import EcosystemIcon from './icons/IconEcosystem.vue'
import CommunityIcon from './icons/IconCommunity.vue'
import SupportIcon from './icons/IconSupport.vue'
import Carousel from 'primevue/carousel';
</script>

<template>
  <section id="contacts">
    <p class="primary">Contacts</p>
    <div class="tiles">
      <div class="tile vertical">
        <div class="tile" style="flex: 7;">
          <a class="tile black filled" href="https://github.com/Komptip" target="_blank">
            <img src="/src/assets/github.svg" alt="">My Github
          </a>
            <div class="tile vertical">
            <a class="tile white filled" href="tel:+48-501-415-402">
              Phone
              <div class="content">
                +48 501 415 402
              </div>
            </a>
            <div class="tile" style="flex: 1;">
              <a class="tile white filled" href="https://www.linkedin.com/in/komptip/" target="_blank">
                <img src="/src/assets/linkedin.svg" width="50">LinkedIn
              </a>
            </div>
          </div>
        </div>
        <a class="tile black filled" href="mailto:komptip@gmail.com">
          Email
          <div class="content">
            komptip@gmail.com
          </div>
        </a>
      </div>
    </div>
  </section>
</template>
<script>
  export default {
    data() {
      return {
        toggled: {
          phone: false,
          email: false
        }
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
  p.primary {
    font-size: 3rem;
    text-align: center;
  }

  .tiles {
    display: flex;
    height: 600px;
  }

  .tile {
    display: flex;
    flex-grow: 1;

    gap: 2rem;

    transition: 0.6s;

    position: relative;

    .content {
      position: absolute;
      width: 100%;
      height: 100%;

      opacity: 0;
        transition: 1s; 

      display: flex;
      align-items: center;
      justify-content: center;
    }

    &.filled {
      justify-content: center;
      align-items: center;
      cursor: pointer;

      font-size: 3rem;
    }

    &.vertical {
      flex-direction: column;
    }

    &.black, &.black .content {
      background-color: black;
      color: white;
    }

    &.white, &.white .content {
      background-color: white;
      color: black;
    }

    &.filled:hover {
      filter: invert(1);

      .content {
        opacity: 1;

        transition: 1s;
      }
    }

  }

  @media screen and (max-width: 1300px){
    .tiles {    
      height: auto;
    }

    .tile {
      flex-direction: column;

      &.filled {
        padding-top: 3rem;
        padding-bottom: 3rem;
      }
    }

    section {
      margin-bottom: 5rem;
    }
  }
</style>


