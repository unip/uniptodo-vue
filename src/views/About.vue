<template>
  <div id="about" class="flex flex-col">
    <div class="container p-4">
      <h1 class="text-3xl font-black">About</h1>
      <p>
        A project by <a href="https://github.com/unip" target="_blank">@unip</a> to explore Vue JS feature using vue-cli.
        Created through <a href="https://youtu.be/Wy9q22isx3U" target="_blank">Brad Traversy tutorial</a>. 
      </p>

      <h3 class="font-black">Used plugins:</h3>
      <ul class="list-disc list-inside mb-3">
        <li><a href="https://jsonplaceholder.typicode.com/" target="_blank">JSON Placeholder</a></li>
        <li><a href="https://tailwindcss.com" target="_blank">Tailwindcss</a></li>
        <li><a href="https://fontawesome.com" target="_blank">Fontawesome</a></li>
      </ul>
      <p>&copy; {{ new Date().getFullYear() }}</p>
    </div>
  </div>
</template>
