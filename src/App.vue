<template>
  <transition name="fade" mode="out-in">

<component :is="selectedComponent"></component>
  </transition>

  <navigation-menu @selected-item="changeComponent"></navigation-menu>
</template>

<script>
import NavigationMenu from './components/NavigationMenu.vue'
import MessagesComponent from './components/MessagesComponent.vue'
import FavoriteAnimals from './components/FavoriteAnimals.vue'

export default {
  name: 'App',
  data(){
    return {
      selectedComponent: 'messages-component'
    }
  },
  components: {
    NavigationMenu,
    MessagesComponent,
    FavoriteAnimals
  },
  methods: {
    changeComponent(id) {
      console.log(id)
      this.selectedComponent = id == 'messages'? 'messages-component': 'favorite-animals'
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.fade-enter-active, .fade-leave-active {
    transition: opacity .25s;
}

.fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
    opacity: 0;
}
</style>
