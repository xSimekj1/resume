<template>
  <div id="app">
    <menu-component/>
    <transition name="fade">
      <router-view/>
    </transition>
  </div>
</template>

<script>
import MenuComponent from './components/MenuComponent.vue';

export default {
  name: 'App',
  components: {
    MenuComponent,
  },
};
</script>

<style lang="less">
@import './assets/styles/global.less';

#app {
  width: 100%;
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s;
}

.fade-enter,
.fade-leave-to {
  opacity: 0;
}

</style>
