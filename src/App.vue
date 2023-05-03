<template>
  <div>
    <main>
      <router-view />
    </main>
  </div>
</template>

<style lang="sass">

</style>

<script>
import { ref } from 'vue'
import Navbar from './components/Navbar.vue'

export default {
  components: {
    Navbar
  }
}
let counter = ref(0)

setInterval(() => {
  counter.value++
}, 1000)
</script>