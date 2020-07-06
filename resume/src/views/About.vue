<template>
  <div class="about">
    <content-component/>
  </div>
</template>

<script>
// @ is an alias to /src
import ContentComponent from '@/components/ContentComponent.vue';

export default {
  name: 'Home',
  components: {
    ContentComponent,
  },
};
</script>
