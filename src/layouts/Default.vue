<template>
<div>
  <div class="bg-gray-100">
    <g-image class="m-6" src="~/assets/logo.png" width="44" /> 
    <div class="flex">
      <!-- card sm md -->
      <div class="px-5 py-8 xl:max-w-md sm:max-w-xl mx-auto lg:w-1/2 lg:max-w-full lg:py-24 lg:px-12">
        <g-image class="mt-6 rounded-lg shadow-xl sm:mt-8 sm:h-64 sm:object-cover sm:object-center  lg:hidden" src="~/assets/11.jpg"/> 
        <h1 class="mt-6 text-xl md:text-2xl sm-mt-8 font-bold text-gray-900 leading-tight">You can work from anywhere. <br>
          <span class="text-indigo-700">Take advantage of that.</span> 
        </h1>
        <p class="mt-2 sm:mt-4 text-gray-600 text-base">Lorem ipsum dolor sit amet consectetur adipisicing elit. Voluptatem nostrum odio dolorum, delectus quaerat exercitationem, quae, a eius eveniet quia vitae eaque. Eum, cupiditate. Ipsum dolorem ipsa eligendi est excepturi!</p>
        <div class="mt-4">
          <a href="#" class="inline-block bg-indigo-500 md:hover:bg-gray-600 hover:bg-indigo-600 focus:shadow-outline active:bg-indigo-800 text-sm text-white px-4 py-3 rounded-md shadow-lg hover:shadow-xl uppercase tracking-wider font-semibold">Book your escape</a>
        </div>
      </div>
      <!-- card sm md -->

      <!-- card lg image left -->
      <div class="hidden lg:block lg:w-1/2 lg:relative">
        <g-image class="mt-6 rounded-lg shadow-xl sm:mt-8 h-full w-full object-cover object-center absolute inset-0" src="~/assets/11.jpg"/> 
      </div>
      <!-- card lg image left -->
    </div>
    
  </div>





  <div class="bg-gray-900 my-12">
      <strong>
        <g-link to="/">{{ $static.metadata.siteName }}</g-link>
      </strong>
      <nav class="nav">
        <g-link class="nav__link" to="/">Home</g-link>
        <g-link class="nav__link" to="/about/">About</g-link>
      </nav>
    <slot/>
  </div>
</div>
</template>

<static-query>
query {
  metadata {
    siteName
  }
}
</static-query>

<style>

</style>
