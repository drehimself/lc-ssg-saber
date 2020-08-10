<template>
  <div>
    <NavigationMain/>
    <slot name="default" />
  </div>
</template>

<script>
// import '../main.css'
import NavigationMain from '../components/NavigationMain.vue'

export default {
  props: ['page'],
  head() {
    const pageTitle = this.page.title
    return {
      title: pageTitle ?
        `${pageTitle} - ${this.$siteConfig.title}` :
        this.$siteConfig.title
    }
  },
  components: {
    NavigationMain,
  }
}
</script>

<style>

</style>
