<template>
  <div>
    <NavigationMain/>

    <div class="markdown-body">
      <h2>{{ page.title }}</h2>
      <div>By: {{ page.author }}</div>
      <slot name="default" />
    </div>
  </div>
</template>

<script>
import 'github-markdown-css/github-markdown.css'
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
  .markdown-body {
		box-sizing: border-box;
		min-width: 200px;
		max-width: 980px;
		margin: 0 auto;
		padding: 45px;
	}

	@media (max-width: 767px) {
		.markdown-body {
			padding: 15px;
		}
	}
</style>
