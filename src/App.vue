<template>
  <button @click="add">
    ADD
  </button>
  <h1>{{ reversedMessage }}</h1>
  <h1>{{ reversedMessage }}</h1>
  <h1>{{ reversedMessage }}</h1>
  <h1>{{ reversedMessage }}</h1>
</template>

<script>
export default {
  data() {
    return {
      // Getter, Setter 둘 다 사용 가능
      msg: 'Hello Computed!'
    }
  },
  computed: {
    // 계산된 하나의 데이터
    // 캐싱이라는 기능 때문에 캐싱된 값을 사용하여 다시 한번 연산하지 않는다(여러번 사용할 경우)
    // 값을 얻어내는 방식으로만 사용 : Getter
    // reversedMessage() {
    //   return this.msg.split('').reverse().join('')
    // }

    // Getter, Setter
    reversedMessage: {
      get() {
        // 계산된 데이터가 값을 얻어내는 용도의 로직 추가
        return this.msg.split('').reverse().join('')
      },
      set(value) {
        // 값 할당 시 실행, 어떠한 로직을 동작 시킬 것인지를 추가
        this.msg = value 
        console.log(value)
      }
    }

  },
  methods: {
    add() {
      this.reversedMessage += '!?'
      // this.msg += '?!'
    }
  }
}
</script>