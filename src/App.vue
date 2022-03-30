<template>
  <h1 @click="increase">
    {{ count }} / {{ doubleCount }}
  </h1>
  <h1 @click="ChangeMessage">
    {{ message }} / {{ reversedMessage }}
  </h1>
</template>

<script>
export default {
  data() {
    return {
      count: 0,
      message: 'Hello World!'
    }
  },
  //computed
  //계산한 후 return을 받을 때 사용하는 옵션
  computed: {
    doubleCount() {
      return this.count * 2
    },
    reversedMessage() {
      return this.message.split('').reverse().join('')
    },
  },

  watch: {
    message(newValue) {
      console.log(newValue)
    }
  },
  //created() 
  //html 부분과 연결되기 전에 실행
  created() {
    console.log(this.message)
  },
  //mounted()
  //html 부분과 연결된 후 실행
  mounted() {
    console.log(this.count)
  },

  methods: {
    increase() {
      this.count += 1
    },
    changeMessage() {
      this.message = "Good?!"
    }
  }
}
</script>