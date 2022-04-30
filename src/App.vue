<template>
  <div :class="{hiddenScroll: hiddenScroll}" class="wrapper">
    <app-header />
    <app-main :years="howOld" :name="devName" />
    <app-footer />
  </div>
</template>

<script>
import AppHeader from './components/AppHeader.vue'
import AppMain from './components/AppMain.vue'
import AppFooter from './components/AppFooter.vue'
export default {
  name: 'App',
  data() {
    return {
      howOld: 17,
      devName: 'Хохлов Даниил',
      hiddenScroll: false,
    }
  },
  components: {
    AppHeader,
    AppMain,
    AppFooter,
  },
}
</script>

<style>
@import url('./assets/styles/style.css');
</style>
