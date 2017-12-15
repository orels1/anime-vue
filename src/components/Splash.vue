<template lang="pug">
  div(:class="$style.splash")
    div(
      :class="$style.anime"
      :style="{ backgroundImage: `url(${image})` }"
    )
      div(:class="$style.frame")
      div(:class="$style.title") {{title}}
      div(:class="$style.score") {{score}}
      div(:class="$style.overlay")
</template>

<script>
import Vue from 'vue';
import Component from 'vue-class-component';

@Component({
  props: {
    title: { type: String, default: 'Title' },
    image: { type: String, default: '' },
    score: { type: Number, default: 5 },
  },
})
export default class Splash extends Vue {
}
</script>

<style lang="sass" module>
.splash
  font-family: 'Avenir', Helvetica, Arial, sans-serif
  font-size: 13px
  -webkit-font-smoothing: antialiased
  -moz-osx-font-smoothing: grayscale
  color: #fff
  width: 680px
  height: 400px
  display: flex
  overflow: hidden

.anime
  position: relative
  border-radius: 4px
  background-position: center center
  background-size: cover
  dislay: flex
  flex-direction: column
  padding: 10px
  width: 100%
  opacity: .9

.frame
  position: relative
  width: 100%
  height: 100%
  display: flex
  flex-direction: column
  border: 1px solid rgba(255,255,255,.5)
  z-index: 10

.title
  position: absolute
  font-size: 30px
  bottom: 20px
  left: 30px
  z-index: 11

.score
  position: absolute
  font-size: 600px
  line-height: 600px
  z-index: 11
  color: rgba(255,255,255,.4)
  top: -80px
  right: 0
  align: right
  letter-spacing: -100px

.overlay
  position: absolute
  left: 0
  top: 0
  width: 100%
  height: 100%
  background: linear-gradient(to bottom, rgba(0,0,0,0) 0%,rgba(0,0,0,0) 47%,rgba(0,0,0,0.8) 100%)
</style>
