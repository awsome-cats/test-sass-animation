<template>
  <div>
    Home
    <space/>
    <animation/>
  </div>
</template>

<script>
// @ is an alias to /src

import Animation from '../components/Animation'
import Space from '../components/utilities/Space.vue'
export default {
  name: 'Home',
  components: {
    Animation,
    Space
  }
}
</script>
