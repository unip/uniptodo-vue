<template>
  <div id="app" class="flex flex-col h-full">
    <Header />
    <router-view/>
  </div>
</template>

<script>
import Header from './components/Header'

export default {
  name: 'app',
  components: {
    Header    
  }
}
</script>