<template lang="pug">
  div(:class="$style.post")
    Splash(:title="title" :image="image" :score="score")
    div(:class="$style.content")
      VueMarkdown(:source="text")
    div(:class="$style.separator")
</template>

<script>
import Vue from 'vue';
import Component from 'vue-class-component';
import VueMarkdown from 'vue-markdown';
import Splash from '@/components/Splash';
import image from '@/assets/image-2.jpg';

@Component({
  components: {
    Splash,
    VueMarkdown,
  },
  props: {
    gistId: { type: String, default: '' },
  },
})
export default class Post extends Vue {
  image=image
  title='Your Name'
  score=9
  text=''

  async mounted() {
    if (this.gistId.length) {
      const resp = await fetch(`https://api.github.com/gists/${this.gistId}`);
      const json = await resp.json();
      const filename = Object.keys(json.files)[0];
      this.text = json.files[filename].content;
    }
  }
}
</script>

<style lang="sass" module>
.post
  font-family: 'Avenir', Helvetica, Arial, sans-serif
  font-size: 13px
  -webkit-font-smoothing: antialiased
  -moz-osx-font-smoothing: grayscale
  color: #fff

.content
  margin: 20px 0 40px 0
  border-radius: 4px
  background: #fcfcfc
  color: rgb(24,24,24)
  padding: 10px 20px
  font-size: 14px
  line-height: 20px

.separator
  margin: 20px 0
  width: 100%
  border-bottom: 1px solid rgba(255,255,255,1)
</style>
