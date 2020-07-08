<template>
  <div class="bg-gray-100">
      <div class="px-5 py-8">
        <g-image src="~/assets/logo.png" width="44"/> 
        <g-image class="mt-6 rounded-lg shadow-xl" src="~/assets/11.jpg" height="400" fit="inside" /> 
        <h1 class="mt-6 text-2xl font-bold text-gray-900 leading-tight">You can work from anywhere. 
          <span class="text-indigo-700">Take advantage of that.</span> 
        </h1>
        <p class="mt-2 text-gray-600">Lorem ipsum dolor sit amet consectetur adipisicing elit. Voluptatem nostrum odio dolorum, delectus quaerat exercitationem, quae, a eius eveniet quia vitae eaque. Eum, cupiditate. Ipsum dolorem ipsa eligendi est excepturi!</p>
      </div>
      <div class="mt-0 mx-5">
        <a href="#" class="inline-block bg-indigo-500 text-sm text-white px-4 py-3 rounded-md shadow-lg uppercase tracking-wider font-semibold">Book your escape</a>
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
