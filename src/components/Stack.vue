<script setup>
import Chart from 'primevue/chart';
import InputText from 'primevue/inputtext';
import 'primevue/resources/themes/lara-dark-indigo/theme.css'

</script>

<template>
  <section id="stack">
    <p class="primary">My stack</p>
    <InputText placeholder="Search..." class="w-full mb-3" v-model="search" />
    <div class="categories">
      <div v-for="category, key in categories" class="category" :class="activeCategories.includes(key) ? 'active' : ''" :style="'background-color:' + category.color" @click="activeCategories.includes(key) ? activeCategories.splice(activeCategories.indexOf(key), 1) : activeCategories.push(key)">
        <i :class="category.icon"></i> {{ category.text }} <span>{{ tags.filter(tag => tag.categories.includes(key) && tag.text.toLowerCase().includes(search.toLowerCase())).length }}</span>
      </div>
    </div>
    <div class="items">
      <template v-for="tag in tags">
        <transition name="fade">
          <div class="item" :class="tag.width + ' ' + tag.height" :style="'background-color:' + tag.bgColor + '; color:' + tag.color + '; font-size:' + tag.fontSize" v-if="(activeCategories.length === 0 || tag.categories.some(category => activeCategories.includes(category))) && tag.text.toLowerCase().includes(search.toLowerCase())">{{ tag.text }}</div>
        </transition>
      </template>
    </div>
  </section>
</template>
<script>
  export default {
    data() {
      return {
        activeCategories: [],
        search: '',
        categories: {
          'backend': {
            'text': 'Backend',
            'icon': 'pi pi-server',
            'color': '#00c851'
          },
          'frontend': {
            'text': 'Frontend',
            'icon': 'pi pi-desktop',
            'color': '#3f51b5'
          },
          'tools': {
            'text': 'Tools',
            'icon': 'pi pi-wrench',
            'color': '#ff4081'
          }
        },
        tags: [
          {
            text: 'Laravel',
            color: 'white',
            bgColor: '#d5b08a',
            width: 'wide',
            height: 'tall',
            fontSize: '3rem',
            categories: ['backend']
          },
          {
            text: 'Vue 3',
            color: 'white',
            bgColor: '#41b883',
            width: 'wide',
            height: '',
            fontSize: '1.4rem',
            categories: ['frontend']
          },
          {
            text: 'Vue 2',
            color: 'white',
            bgColor: '#34495e',
            width: '',
            height: '',
            fontSize: '1.7rem',
            categories: ['frontend']
          },
          {
            text: 'PHP',
            color: 'white',
            bgColor: '#777bb4',
            width: '',
            height: 'tall',
            fontSize: '1.4rem',
            categories: ['backend']
          },
          {
            text: 'Python',
            color: 'white',
            bgColor: '#3572a5',
            width: '',
            height: '',
            fontSize: '1.4rem',
            categories: ['backend']
          },
          {
            text: 'Symfony',
            color: 'white',
            bgColor: '#000000',
            width: '',
            height: '',
            fontSize: '1.4rem',
            categories: ['backend']
          },
          {
            text: 'HTMX',
            color: 'white',
            bgColor: '#e34c26',
            width: '',
            height: '',
            fontSize: '1.4rem',
            categories: ['frontend']
          },
          {
            text: 'Nuxt',
            color: 'white',
            bgColor: '#000000',
            width: '',
            height: '',
            fontSize: '1.4rem',
            categories: ['backend']
          },
          {
            text: 'Next',
            color: 'white',
            bgColor: '#000000',
            width: '',
            height: '',
            fontSize: '1.4rem',
            categories: ['backend']
          },
          {
            text: 'CSS',
            color: 'white',
            bgColor: '#067df7',
            width: 'wide',
            height: 'tall',
            fontSize: '1.4rem',
            categories: ['frontend']
          },
          {
            text: 'SCSS',
            color: 'white',
            bgColor: '#cd6799',
            width: '',
            height: '',
            fontSize: '1.4rem',
            categories: ['frontend']
          },
          {
            text: 'SASS',
            color: 'white',
            bgColor: '#cd6799',
            width: '',
            height: '',
            fontSize: '1.4rem',
            categories: ['frontend']
          },
          {
            text: 'JavaScript',
            color: 'white',
            bgColor: '#f7df1e',
            width: 'wide',
            height: 'tall',
            fontSize: '1.4rem',
            categories: ['frontend']
          },
          {
            text: 'Express',
            color: 'white',
            bgColor: '#000000',
            width: '',
            height: '',
            fontSize: '1.4rem',
            categories: ['backend']
          },
          {
            text: 'HTML',
            color: 'white',
            bgColor: '#e34c26',
            width: '',
            height: '',
            fontSize: '1.4rem',
            categories: ['frontend']
          },
          {
            text: 'SQL',
            color: 'white',
            bgColor: '#00758f',
            width: 'wide',
            height: 'tall',
            fontSize: '1.4rem',
            categories: ['backend']
          },
          {
            text: 'SQL CTE',
            color: 'white',
            bgColor: '#00758f',
            width: '',
            height: '',
            fontSize: '1.4rem',
            categories: ['backend']
          },
          {
            text: 'Git',
            color: 'white',
            bgColor: '#f05032',
            width: '',
            height: '',
            fontSize: '1.4rem',
            categories: ['tools']
          },
          {
            text: 'Linux',
            color: 'white',
            bgColor: '#f9a602',
            width: '',
            height: '',
            fontSize: '1.4rem',
            categories: ['tools']
          },
          {
            text: 'Opencart 2/3/4',
            color: 'white',
            bgColor: '#e96707',
            width: 'wide',
            height: '',
            fontSize: '1.4rem',
            categories: ['backend']
          },
          {
            text: 'Wordpress',
            color: 'white',
            bgColor: '#21759b',
            width: '',
            height: '',
            fontSize: '1.4rem',
            categories: ['backend']
          },
          {
            text: 'Netcat CMS',
            color: 'white',
            bgColor: '#000000',
            width: '',
            height: '',
            fontSize: '1.4rem',
            categories: ['backend']
          },
          {
            text: 'Shopify',
            color: 'white',
            bgColor: '#00848e',
            width: '',
            height: '',
            fontSize: '1.4rem',
            categories: ['backend']
          },
          {
            text: 'jQuery',
            color: 'white',
            bgColor: '#0769ad',
            width: '',
            height: '',
            fontSize: '1.4rem',
            categories: ['frontend']
          },
          {
            text: 'GLSL',
            color: 'white',
            bgColor: '#000000',
            width: '',
            height: '',
            fontSize: '1.4rem',
            categories: ['frontend']
          },
          {
            text: 'Three.js',
            color: 'white',
            bgColor: '#000000',
            width: '',
            height: '',
            fontSize: '1.4rem',
            categories: ['frontend']
          },
          {
            text: 'webGL',
            color: 'white',
            bgColor: '#000000',
            width: 'wide',
            height: '',
            fontSize: '1.4rem',
            categories: ['frontend']
          },
          {
            text: 'React',
            color: 'white',
            bgColor: '#61dafb',
            width: '',
            height: '',
            fontSize: '1.4rem',
            categories: ['frontend']
          },
          {
            text: 'Node.js',
            color: 'white',
            bgColor: '#339933',
            width: '',
            height: '',
            fontSize: '1.4rem',
            categories: ['backend']
          },
          {
            text: 'Apache jMeter',
            color: 'white',
            bgColor: '#f05032',
            width: '',
            height: '',
            fontSize: '1.4rem',
            categories: ['tools']
          },
          {
            text: 'Postman',
            color: 'white',
            bgColor: '#f05032',
            width: '',
            height: '',
            fontSize: '1.4rem',
            categories: ['tools']
          },
          {
            text: 'VSCode',
            color: 'white',
            bgColor: '#007acc',
            width: 'wide',
            height: 'tall',
            fontSize: '1.4rem',
            categories: ['tools']
          },
          {
            text: 'Obsidian',
            color: 'white',
            bgColor: '#000000',
            width: '',
            height: '',
            fontSize: '1.4rem',
            categories: ['tools']
          },
          {
            text: 'Docker',
            color: 'white',
            bgColor: '#2496ed',
            width: '',
            height: '',
            fontSize: '1.4rem',
            categories: ['tools']
          },
          {
            text: 'Github Actions',
            color: 'white',
            bgColor: '#24292e',
            width: '',
            height: '',
            fontSize: '1.4rem',
            categories: ['tools']
          },
          {
            text: 'Github Copilot',
            color: 'white',
            bgColor: '#4285f4',
            width: '',
            height: '',
            fontSize: '1.4rem',
            categories: ['tools']
          },
          {
            text: 'Augment Code',
            color: 'white',
            bgColor: '#007acc',
            width: '',
            height: '',
            fontSize: '1.4rem',
            categories: ['tools']
          },
          {
            text: 'AWS',
            color: 'white',
            bgColor: '#ff9900',
            width: '',
            height: '',
            fontSize: '1.4rem',
            categories: ['tools']
          },
          {
            text: 'DBeaver',
            color: 'white',
            bgColor: '#000000',
            width: '',
            height: '',
            fontSize: '1.4rem',
            categories: ['tools']
          },
          {
            text: 'PHPMyAdmin',
            color: 'white',
            bgColor: '#000000',
            width: '',
            height: '',
            fontSize: '1.4rem',
            categories: ['tools']
          },
          {
            text: 'SourceTree',
            color: 'white',
            bgColor: '#000000',
            width: '',
            height: '',
            fontSize: '1.4rem',
            categories: ['tools']
          },
          {
            text: 'NPM',
            color: 'white',
            bgColor: '#cb3837',
            width: '',
            height: '',
            fontSize: '1.4rem',
            categories: ['tools']
          },
          {
            text: 'Rust',
            color: 'white',
            bgColor: '#000000',
            width: '',
            height: '',
            fontSize: '1.4rem',
            categories: ['backend']
          },
          {
            text: 'PHPUnit',
            color: 'white',
            bgColor: '#000000',
            width: '',
            height: '',
            fontSize: '1.4rem',
            categories: ['tools', 'backend']
          },
          {
            text: 'Expose.dev',
            color: 'white',
            bgColor: '#000000',
            width: '',
            height: '',
            fontSize: '1.4rem',
            categories: ['tools']
          }
        ]
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
    gap: 1rem;
    
    margin-top: 2rem;
    margin-bottom: 2rem;
  }

  .categories {
    display: flex;
    flex-wrap: wrap;
    gap: 1rem;

    .category {
      display: flex;
      align-items: center;
      gap: 0.4rem;

      padding-right: 1.3rem;

      border-radius: 5rem;

      border: 1px solid transparent;

      cursor: pointer;

      i {
        border: 1px solid white;
        height: 100%;
        aspect-ratio: 1;

        display: flex;
        align-items: center;
        justify-content: center;

        padding: 0.5rem;

        border-radius: 5rem;
      }

      span {
        font-weight: bolder;
      }

      &.active {
        border-color: white;
      }
    }
  }

  .items {
    display: grid;
    grid-gap: 15px;
    grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
    grid-auto-rows: 150px;
    grid-auto-flow: dense;

    .item {
      display: flex;
      align-items: center;
      justify-content: center;

      padding: 2rem;
      box-sizing: border-box;
      text-align: center;
    }

    .small {
      grid-column: span 1;
    }

    .wide {
      grid-column: span 2;
    }

    .tall {
      grid-row: span 2;
    }
  }

  p.primary {
    font-size: 3rem;
    text-align: center;
  }

  .fade-enter-active, .fade-leave-active {
    transition: opacity .5s;
  }
  .fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
    opacity: 0;
  }

  @media screen and (max-width: 1300px){
    .split {
      flex-direction: column;
    }
  } 
</style>


