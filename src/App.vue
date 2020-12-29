<template>
  <div>
  <Navbar />
  <Input />
  </div>
</template>

<script>
import Navbar from './components/Navbar.vue'
import Input from './components/Input.vue'

export default {
  name: 'App',
  components: {
    Navbar,
    Input
  }
}
</script>

