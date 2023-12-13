<script>
export default {
  data(){
    return {
      info: 'Title',
      someInfo: 'Anons of message'
    }
  },
  methods: {
    userData(word= 'New text') {
     
      // this.info = 'Some new'
      this.someInfo = word
    }
  },
}
</script>

<template>
  <h3>{{ info }}</h3>
  <p>{{ someInfo }}</p>

  <button type ="button" @click="userData()">Отправить</button>
</template>

<style scoped>
h3{
  font-weight: lighter;
}

p {
    color: rgb(222, 66, 66);
}
</style>
