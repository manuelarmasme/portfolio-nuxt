<template>
  <div class="flex space-x-2 items-center">
    <div class="text-gray-500 text-xs" v-if="showNextModelLabel"> Change to {{ nextMode }}</div>
    <button
      @mouseenter="showNextModelLabel = true"
      @mouseleave="showNextModelLabel = false"
      class="hover:bg-gray-200 dark:hover:bg-gray-600 px-2 py-1 text-gray-500 text-4xl md:text-base"
      @click="toggleMode"
      >{{ nextModeIcon }}</button>
  </div>
</template>

<script setup>
const showNextModelLabel = ref(false)

//setting colormode composable
const colorMode = useColorMode()

// mode options
const modes = [
  'system',
  'light',
  'dark'
]

//icon dark mode
const nextModeIcons = {
  system: '🌓',
  light: '🌕',
  dark: '🌑'
}

const nextMode = computed(()=>{
  //get the index array option
  const currentModeIndex = modes.indexOf(colorMode.preference)

  //control de index
  let nextModeIndex = null

  if (currentModeIndex + 1 === modes.length) {
    nextModeIndex = 0
  } else {
    nextModeIndex = currentModeIndex + 1
  }

  return modes[nextModeIndex]
})

//icon computed
const nextModeIcon = computed(() => nextModeIcons[nextMode.value])

//toggle function to change mode
const toggleMode = () => colorMode.preference = nextMode.value

</script>