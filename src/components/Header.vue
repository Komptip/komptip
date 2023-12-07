<script setup>
  import 'primeicons/primeicons.css'
</script>

<template>
  <i :class="{'toggled': toggled}" class="nav-toggle pi pi-align-justify" @click="toggled = !toggled"></i>
  <header :class="{'toggled': toggled}"  @click="toggled = !toggled">
    <a href="#stack">Skills</a>
    <a href="#portfolio">Portfolio</a>
    <a href="#faq">FAQ</a>
    <a href="#contacts">Contacts</a>
  </header>
</template>
<script>
  export default {
    data() {
      return {
        toggled: false
      }
    }
  };
</script>
<style lang="scss" scoped>
  .nav-toggle {
    position: fixed;
    font-size: 2rem;

    display: none;
    right: 0px;
    top: 0px;

    opacity: 1;
    transition: opacity 0.2s;

    background-color: var(--vt-c-soft-transparent);
    padding: 1.4rem;

    z-index: 10;

    &.toggled {
      opacity: 0;

      transition: 0.2s;
    }
  }

  header {
      width: 100%;
      height: 5rem;

      position: absolute;
      left: 0;
      top: 0px;

      gap: 1.5rem;

      display: flex;
      justify-content: center;
  }

  a {
    display: flex;
    align-items: center;

    font-size: 1.3rem;
    padding: 1rem;

    color: white;

    cursor: pointer;
  }

  
  @media (max-width: 600px) {
    .nav-toggle {
      display: block;
    }

    header {
      position: fixed;

      background-color: var(--vt-c-hard-transparent);

      height: 100vh;
      flex-direction: column;
      justify-content: center;
      align-items: center;

      z-index: 2;
      opacity: 1;

      transition: opacity 0.2s;

      &:not(.toggled){
        opacity: 0;
        
        pointer-events: none;

        transition: 0.2s;
      }
    }
  }

</style>


