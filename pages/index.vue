<template>
  <article class="prose dark:prose-invert max-w-none">
    <ContentDoc path="/"/>
  </article>
</template>

<script setup>
useSeoMeta({
  title: 'Main page',
  description: 'This is the Main page',
  ogTitle: 'Main page',
  ogDescription: '[og:description]',
  ogImage: '[og:image]',
  ogUrl: '[og:url]',
  twitterTitle: 'Main page',
  twitterDescription: '[twitter:description]',
  twitterImage: '[twitter:image]',
  twitterCard: 'summary'
})

useHead({
  htmlAttrs: {
    lang: 'en'
  },
  link: [
    {
      rel: 'icon',
      type: 'image/png',
      href: '/favicon.png'
    }
  ]
})
</script>