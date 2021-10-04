<template>
  <div>
    <frame></frame>
  </div>
</template>

<script>
import Frame from './components/Frame'

export default {
  name: 'App',
  components: {
    Frame
  }
}
</script>

<style>
@import url(./assets/css/normalize.css);

html {
  background-color: #F9F9F9;
}
</style>
