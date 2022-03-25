<template>
  <button @click="add">ADD</button>
  <h1>{{ reversedMessage }}</h1>
  <h1>{{ reversedMessage }}</h1>
  <h1>{{ reversedMessage }}</h1>
  <h1>{{ reversedMessage }}</h1>
</template>

<script>
export default {
  data() {
    return {
      // Getter, Setter
      msg: "Hello Computed"
    }
  },
  computed: { // computed 에 만들어놓은 계산된 데이터는 캐싱을 통해 한번 연산을 한 값이 있으면 또 다시 연산하지 않는다
  // Getter (읽기전용)
    // reversedMessage() {
    //   return this.msg.split('').reverse().join('')
    // }
    // Getter, Setter
    reversedMessage: {
      get() {
        return this.msg.split('').reverse().join('')
      },
      set(value) {
        this.msg = value
        console.log(value)
      }
    }
  },
  methods: {
    add() {
      this.reversedMessage += '!?'
    }
  }
  
}
</script>