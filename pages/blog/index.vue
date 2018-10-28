<template>
  <div>
    All blog posts
    <ul>
      <li
      v-for="(post, index) in allPosts"
      :key="index"
    >
      <h2>
        <nuxt-link :to="`/blog/${post.slug}`">
          {{ post.title }}
        </nuxt-link>
      </h2>
      <p>{{ post.text }}</p>
      </li>
    </ul>
  </div>
</template>

<script>
import gql from 'graphql-tag'

export default {
apollo: {
allPosts: gql`{
allPosts {
title
text
slug
}
}'
}
}
</script>
