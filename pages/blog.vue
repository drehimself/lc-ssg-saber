<template>
  <div>
    <h2>Posts</h2>
    <ul>
      <li v-for="post in page.posts" :key="post.permalink">
        <a :href="post.permalink">{{ post.title }}</a>
      </li>
    </ul>
  </div>
</template>

<script>
export const data = {
  layout: 'default',
  injectAllPosts: true,
  title: 'Blog',
}

export default {
  props: ['page']
}
</script>

<style>

</style>
