<template>
  <headerSection/>
  <mainSection/>
</template>

<script>
import headerSection from '@/components/headerSection.vue'
import mainSection from '@/components/mainSection.vue'
export default {
  name: 'App',
  components: {
    headerSection,
    mainSection
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
