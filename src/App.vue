<template>
  <!-- Remove & use example component! -->
  <HelloWorld 
    :msg="message" 
    @click="handler" />
  <HelloWorld msg="Good" />
</template>

<script>
import HelloWorld from '~/components/HelloWorld'

export default {
  components: {
    HelloWorld
  },
  data() { //data: function () {} 의 축약형
    return {
      message: 'Hello Vue!' //variable: 값 // 변수 선언 방식
    }
  },
  methods: {
    handler() {
      console.log(this.message)
      this.message += '!'
    }
  }
}
</script>