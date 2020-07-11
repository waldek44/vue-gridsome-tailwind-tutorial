<template>
<div class=" relative">
  <button @click="isOpen = !isOpen" class="relative z-10 block h-8 w-8 rounded-full overflow-hidden border-3 border-gray-600 focus:outline-none">
    <g-image contain="w-full h-full object-cover" src="~/assets/avatar.png" width="44" /> 
  </button>
  <!-- button który tworzy kwadrat na cały viewport i po kliknięciu gdziekolwiek zamyka modal - cool -->
  <button v-if="isOpen" @click="isOpen = false" tabindex="-1" class="fixed inset-0 h-full w-full bg-opacity-75 bg-black cursor-default"></button>
  <div v-if="isOpen" class="absolute right-0 top-auto w-48 mt-3 bg-white rounded-lg py-2 shadow-lg">
    <a href="#" class="block px-4 py-2 hover:bg-indigo-700 hover:text-white">pierwszy</a>
    <a href="#" class="block px-4 py-2 hover:bg-indigo-700 hover:text-white">drugi</a>
    <a href="#" class="block px-4 py-2 hover:bg-indigo-700 hover:text-white">trzeci</a>
  </div>
</div>
</template>

<script>
export default {
  data() {
    return {
      isOpen: false,
    }
  }
}
</script>