<template>
  <div id="app" class="container">

    <h2>
      <span>{{ 'Pomodoro' | lowercase | addspace }} # {{ 'Pomodoro' | uppercase | addspace }}</span>
      <controls-component></controls-component>
      <div v-if="1<5">hello</div>

    </h2>
    <state-title-component v-bind:isworking="isworking"></state-title-component>
    <countdown-component></countdown-component>
    <kittens-component v-show="!isworking"></kittens-component>
  </div>
</template>

<script>
// vue init webpack 05pomodoro

import ControlsComponent from './components/ControlsComponent'
import CountdownComponent from './components/CountdownComponent'
import KittensComponent from './components/KittensComponent'
import StateTitleComponent from './components/StateTitleComponent'

window.data = { kittens:   true,
                isworking: true
              }

export default {
  name: 'App',
  components: {
    ControlsComponent,
    CountdownComponent,
    KittensComponent,
    StateTitleComponent
  },
  data () {
    return window.data
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
