<template>
  <div>
    {{ b }}
  </div>

</template>

<script lang="ts">
import { defineComponent, ref, reactive } from 'vue'
import HelloWorld from './components/HelloWorld.vue'

export default defineComponent({
  name: 'App',
  components: {
    HelloWorld
  },
  setup() {
    const refA = ref(1);
    const reactiveB = reactive({ k: refA });
    console.log(reactiveB.k)

    setTimeout(() => {
      refA.value = Math.random();
    }, 5000);
    return {
      b: reactiveB
    }

  }
})
</script>

<style>
#app {
  color: #2c3e50;
  margin-top: 60px;
}
</style>
