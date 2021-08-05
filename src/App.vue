<template>
  <div>
    {{ a }}
    <button @click="test">test</button>
    <!-- <HelloWorld/> -->
  </div>

</template>

<script lang="ts">
import { defineComponent, ref, reactive, toRefs, computed, watchEffect, triggerRef } from 'vue'
import HelloWorld from './components/HelloWorld.vue'

export default defineComponent({
  name: 'App',
  components: {
    HelloWorld
  },
  setup() {
    const a = ref(1)

    watchEffect(() => {
      console.log('effect', a.value)
    })

    function test() {
      triggerRef(a)
    }

    return {
      a,
      test
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
