<template>
  <h1 @click="increase">
    {{ count }} / {{ doubleCount }}
  </h1>
  <h1 @click="ChangeMessage">
    {{ message }} / {{ reversedMessage }}
  </h1>
</template>

<script>
import { ref, computed, watch, onMounted, } from 'vue'

export default {
  //setup()은 html부분과 아직 연결되기 전에 실행된다
  setup() {
    const count = ref(0)
    function increase() {
      count.value += 1
    }
    const doubleCount = computed(() => {
      return count.value * 2
    })

    
    const message = ref('Hello World!')
    const reversedMessage = computed(() => {
      return message.value.split('').reverse().join('')
    })
    //watch(추적대상, 실행함수)
    watch(message, (newValue) => { console.log(newValue) })
    function changeMessage() {
      message.value = "Good?!"
    }
    console.log(count.value)

    onMounted(() => {
      console.log(message.value)       
    })

    return {
      count,
      doubleCount,
      message,
      increase,
      reversedMessage,
      changeMessage,
    }
  }
}
</script>