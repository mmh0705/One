<template>
  <div id="app">
    <router-view />
    <BottomNavigation />
    <LoadingScreen :isLoading="isLoading" />
    <!-- <div v-if="!isLoading">
    </div> -->
  </div>
</template>

<script lang="ts">
import Vue from "vue";
import Component from "vue-class-component";

import BottomNavigation from "./components/layout/BottomNavigation.vue";
import LoadingScreen from "./components/layout/LoadingScreen.vue";

@Component({
  components: { BottomNavigation, LoadingScreen },
})
export default class App extends Vue {
  public isLoading: boolean = false;
}
</script>

<style>
html,
body {
  margin: 0;
  padding: 0;
  height: 100%;
}
div {
  margin: 0;
  padding: 0;
}
#app {
  background-color: blueviolet;
  height: 100%;
  margin: 0;
}
</style>
