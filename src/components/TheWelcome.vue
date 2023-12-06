<script setup>
import DocumentationIcon from './icons/IconDocumentation.vue'
import ToolingIcon from './icons/IconTooling.vue'
import EcosystemIcon from './icons/IconEcosystem.vue'
import CommunityIcon from './icons/IconCommunity.vue'
import SupportIcon from './icons/IconSupport.vue'
</script>

<template>
  <section>
    <div class="photo"></div>
    <div class="content">
      <p class="text--primary">Hey! I'm Andrii Bondarenko</p>
      <p class="text--secondary">Web developer with knowlange of 
        <a class="tag" href="#stack">PHP</a> 
        <a class="tag" href="#stack">Javascript</a>
        <a class="tag" href="#stack">HTML</a>
        <a class="tag" href="#stack">CSS</a>
        <a class="tag" href="#stack">SASS</a>
        <a class="tag" href="#stack">SCSS</a>
        <a class="tag" href="#stack">Vue</a>
        <a class="tag" href="#stack">jQuery</a>
        <a class="tag" href="#stack">Laravel</a>
        <a class="tag" href="#stack">Git</a>
        <a class="tag" href="#stack">Docker</a>
      </p>
    </div>
  </section>
</template>

<style scoped>
    
  section {
    display: flex;
    align-items: center;

    min-height: 100vh;

    gap: 5rem;
  }

  .photo {
    display: block;

    width: 30rem;
    flex: 1;
    aspect-ratio: 1;

    background-image: url(/src/assets/photo-1.webp);
    background-size: 180%;
    background-position: right 15% top 25%;

    border-radius: 50%;
  }

  .content {

    flex: 2.2;
    
    .text--primary {
      font-size: 3.0rem;
    }

    .text--secondary {
      font-size: 1.2rem;

      .tag {
        background-color: var(--vt-c-soft-transparent);
        color: var(--vt-c-soft-white);
        margin: 0.25rem;
        padding: 0.3rem 1.1rem;
        font-size: 0.85rem;

        border-radius: 0.5rem;
        transition: color 0.5s;

        cursor: pointer;
        display: inline-block;

        &:hover {
          transition: color 0.5s;
          color: var(--color-text);
        }
      }
    }
  }

</style>


