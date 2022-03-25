<template>
  <h1 @click="changeMessage">{{ msg }}</h1>
  <h1>{{ reversedMessage }}</h1>
</template>

<script>
export default {
  data() {
    return {
      msg: 'Hello?'
    }
  },
  computed: {
    reversedMessage() {
      return this.msg.split('').reverse().join('')
    }
  },
  watch: { // 데이터의 변경사항을 감시, 감지가 되면 이후의 로직 실행 // 새로운 매개변수를 할당 가능
    msg(newValue) {
      console.log('msg:', newValue)
    },
    reversedMessage() {
      console.log('reversedMessage:', this.reversedMessage)
    }
  },
  methods: {
    changeMessage() {
      this.msg = 'Good!'
    }
  }
}
</script>