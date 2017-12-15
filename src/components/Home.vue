<template lang="pug">
  #home(:class="$style.container")
    div(:class="$style.topbar")
      div(:class="$style.block")
        div(:class="$style.name") orels1
        div(:class="$style.section") &nbsp;/ Anime
      div(:class="$style.block") @orels1_

    div(:class="$style.list")
      Post(:gistId="list[0]")

</template>

<script>
import Vue from 'vue';
import Component from 'vue-class-component';
import Post from '@/components/Post';

@Component({
  components: {
    Post,
  },
})
export default class Home extends Vue {
  list = ['ed0a6a865052426d74ee4387b823b8da'];
}
</script>

<style lang="sass" module>
.container
  padding: 0 20px
  max-width: 680px
  margin: 0 auto

.topbar
  margin: 20px auto 0px auto
  width: 100%
  max-width: 1200px
  padding: 0 0 20px 0
  line-height: 20px
  display: flex
  justify-content: space-between
  border-bottom: 1px solid rgba(255,255,255,1)

.block
  display: flex

.name
  font-size: 20px
  font-weight: bold

.section
  font-size: 20px

.list
  max-width: 1200px
  margin: 25px auto
  padding: 0 20px
  display: flex
  flex-direction: column
  align-items: center
</style>
