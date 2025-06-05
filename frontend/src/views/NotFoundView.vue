<template>
  <div class="flex-1 flex items-center justify-center min-h-[76vh] min-w-full">
    <div class="bg-white/40 backdrop-blur-lg rounded-xl border border-white/60 p-10 shadow-lg text-center max-w-lg w-full">
      <img
        src="../assets/clouds.png"
        alt="Soleil"
        class="mx-auto  w-48 h-48"
      />
      <div class="text-6xl mb-4"></div>
      <h1 class="text-4xl font-bold text-gray-800 mb-2">404 - Oups !</h1>
      <p class="text-gray-700 mb-6">La page que vous cherchez semble perdue dans les nuages.</p>
      <router-link
        to="/"
        class="bg-black text-white px-6 py-2 rounded-xl shadow hover:bg-gray-800 transition"
      >
        Retour à l'accueil
      </router-link>
    </div>
  </div>
</template>

