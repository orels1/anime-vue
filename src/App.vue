<template lang="pug">
  div(:class="$style.app")
    router-view
</template>

<script>
import Vue from 'vue';
import Component from 'vue-class-component';
// import Navbar from '@/components/Navbar';

@Component({
  // components: {
  //   navbar: Navbar,
  // },
})
export default class App extends Vue {
}
</script>

<style lang="sass" module>
body
  margin: 0
  background: #000;

.app
  font-family: 'Avenir', Helvetica, Arial, sans-serif
  font-size: 13px
  -webkit-font-smoothing: antialiased
  -moz-osx-font-smoothing: grayscale
  color: #fff
</style>
