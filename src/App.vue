<script setup>
import TheWelcome from './components/TheWelcome.vue'
import Portfolio from './components/Portfolio.vue'
import Header from './components/Header.vue'
import Contacts from './components/Contacts.vue'
import FAQ from './components/FAQ.vue'
import Stack from './components/Stack.vue'
import Expirience from './components/Expirience.vue'
</script>

<template>
  <Header/>
  <main>
    <TheWelcome />
    <Stack />
    <Expirience />
    <Portfolio />
    <FAQ/>
    <Contacts/>
  </main>
</template>

<style scoped>
section {

}


@media (min-width: 1024px) {
  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
