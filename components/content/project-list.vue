<template>
  <div class="not-prose">
  <section v-if="pending">Loading list...</section>
  <section v-else-if="error">Something went wrong, try later!</section>
  <section v-else>
    <ul class="grid grid-cols-1 gap-4">
      <li v-for="repository in repos" :key="repository.id" class="border border-gray-200 dark:border-gray-800 roudend-sm p-4 hover:bg-gray-100 font-mono dark:hover:bg-gray-800">
        <a :href="repository.html_url" target="_blank">
          <div class="flex items-center justify-between">

            <div class="font-semibold text-sm">{{ repository.name }}</div>
            <div>{{ repository.stargazers_count }} *</div>
          </div>
          <p>{{ repository.description }}</p>
        </a>
      </li>
    </ul>
  </section>

  </div>
</template>

<script setup>

//fetchin data from github
const {error, pending, data} = await useFetch('https://api.github.com/users/manuelarmasme/repos')


//sort function
const repos = computed(() => data.value.sort((a,b) => a.size - b.size))


</script>