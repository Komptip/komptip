<script setup>
import TheWelcome from './components/TheWelcome.vue'
import Portfolio from './components/Portfolio.vue'
import Header from './components/Header.vue'
import Contacts from './components/Contacts.vue'
import FAQ from './components/FAQ.vue'
import Stack from './components/Stack.vue'
</script>

<template>
  <Header/>
  <main>
    <TheWelcome />
    <Stack />
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
