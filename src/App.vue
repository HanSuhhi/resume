<template>
<div id="app">
  <aside></aside>
  <article class="resume">
    <head-info></head-info>
    <education></education>
    <experience class="experience"></experience>
  </article>
  <aside></aside>
</div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import HeadInfo from './components/HeadInfo.vue';
import Education from './components/Education.vue';
import Experience from './components/Experience.vue';

@Component({
  components: {
    HeadInfo,
    Education,
    Experience,
  },
})
export default class App extends Vue {}
</script>

<style lang="scss">
  #app {
    overflow-x: hidden;
    word-break: break-all;
  }
@media (min-width: 800px)  {
  #app {
    position: absolute;
    left: 0;
    top: 0;
    margin: auto;
    width: 100%;
    background-color: rgba($color: #F5F5F5, $alpha: 1.0);
    text-align: center;
    display: flex;
    font-family: "Microsoft Yahei", arial;
    .resume {
      margin-top: 1rem;
      margin-bottom: 2rem;
      box-shadow: 3px 2px 7px 2px rgba($color: gray, $alpha: .8);
      background-color: white;
    }
    aside {
      flex: 1;
    }
  }
}
@media (max-width: 800px) {
  #app {
    position: absolute;
    left: 0;
    top: 0;
    bottom: 0;
    right: 0;
    margin: auto;
    background-color: rgba($color: #F5F5F5, $alpha: 1.0);
    text-align: center;
    font-family: "Microsoft Yahei", arial;
    .resume {
      box-shadow: 0px 2px 7px 2px rgba($color: gray, $alpha: .8);
      background-color: white;
      .experience {
        padding-bottom: 1rem;
      }
    }
    aside {
      display: none;
    }
  }
}
</style>
