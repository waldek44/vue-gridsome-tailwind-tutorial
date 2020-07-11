<template>
<header class="bg-gray-800 sm:flex sm:items-center sm:justify-between px-4 py-3">
<div class="flex items-center justify-between  px-4 py-3 sm:p-0">
  <!-- left -->
  <div>
    <g-image class="h-10" src="~/assets/logo.png" width="44" /> 
  </div>
  <!-- left -->
  
  <!-- right -->
  <div class="sm:hidden">
<button @click="isOpen = !isOpen" type="button" class="block text-gray-500 hover:text-white focus:text-white focus:outline-none">
          <svg class="h-6 w-6 fill-current" viewBox="0 0 24 24">
            <path v-if="isOpen" fill-rule="evenodd" d="M18.278 16.864a1 1 0 0 1-1.414 1.414l-4.829-4.828-4.828 4.828a1 1 0 0 1-1.414-1.414l4.828-4.829-4.828-4.828a1 1 0 0 1 1.414-1.414l4.829 4.828 4.828-4.828a1 1 0 1 1 1.414 1.414l-4.828 4.829 4.828 4.828z"/>
            <path v-if="!isOpen" fill-rule="evenodd" d="M4 5h16a1 1 0 0 1 0 2H4a1 1 0 1 1 0-2zm0 6h16a1 1 0 0 1 0 2H4a1 1 0 0 1 0-2zm0 6h16a1 1 0 0 1 0 2H4a1 1 0 0 1 0-2z"/>
          </svg>
        </button>
  </div>
  <!-- right -->
</div>
  <!-- linki -->
  <div :class="isOpen ? 'block' : 'hidden'" class="sm:block">
    <div class="px-2 pt-1 pb-4 sm:flex sm:p-0">
    <a href="#" class="block text-white font-semibold hover:bg-gray-600 px-2 py-1 ">pierwszy</a>
    <a href="#" class="block text-white font-semibold hover:bg-gray-600 px-2 py-1 mt-1 sm:mt-0 sm-ml-2">drugi</a>
    <a href="#" class="block text-white font-semibold hover:bg-gray-600 px-2 py-1 mt-1 sm:mt-0 sm-ml-2">trzeci</a>
    <Dropdown class="hidden sm:block ml-6" />
    </div>
    

    <!--tu dodaję dropdawn widoczny tylko na mobile, a orginalny dropdown ukryję -->
    <div class="px-4 py-6 border-t border-gray-600 mt-4 p-2 sm:hidden">
      <div class="flex items-center">
        <g-image contain="w-full h-full object-cover" src="~/assets/avatar.png" width="44" /> 
        <span class="text-white ml-3 font-semibold">Jane Doe</span>
      </div>
      <div class="">
        <a href="#" class="text-gray-400 block mt-2 hover:text-white">pierwszy</a>
        <a href="#" class="text-gray-400 block mt-2 hover:text-white">drugi</a>
        <a href="#" class="text-gray-400 block mt-2 hover:text-white">trzeci</a>
      </div>
    </div>
    <!--tu dodaję dropdawn widoczny tylko na mobile, a orginalny dropdown ukryję -->

  </div>
  <!-- linki -->

</header>
</template>

<script>
import Dropdown from '~/components/Dropdown'
export default {
  components: {
    Dropdown
  },
  data() {
    return {
      isOpen: false,
    }
  }
}
</script>