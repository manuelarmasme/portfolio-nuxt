<template>
  <div>
    Blog post page
  </div>

  <div>
    Blog post id {{ route.params.id }}
  </div>
</template>

<script setup>
const route = useRoute();
</script>