<script setup>
import { ref, onMounted, onUnmounted } from 'vue';

// import HelloWorld from './components/HelloWorld.vue'

const x = ref(0)
const y = ref(0)

onMounted(() => {
  window.addEventListener('mousemove', mouseEvent => {
    x.value = mouseEvent.pageX
    y.value = mouseEvent.pageY
  })
})

onUnmounted(() => {
  window.removeEventListener('mousemove', mouseEvent => {
    x.value = mouseEvent.pageX
    y.value = mouseEvent.pageY
  })
})

</script>

<template>
  <div class="container">
    <div class="test">X: {{ x }}</div>
    <div class="test">Y: {{ y }}</div>
  </div>
</template>

<style scoped>
.container {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  row-gap: 5px;
  background-color: #291e1d;
  width: 100vw;
  height: 100vh;
}

.test {
  color: white;
  font-size: 28px;
}
</style>
