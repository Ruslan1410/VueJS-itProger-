<template>
    <input type ="text" v-model="userName" placeholder="Имя">
    <input type ="password" v-model="userPass" placeholder = "Пароль">
    <input type ="email" v-model="userEmail" placeholder = "Email">
    <button @click ="sendData()">Отправить</button>
    

    <div v-for="(el, index) in users" :key="index">
    <h3>{{  el.name }}</h3>
    <p>Some</p>
    <div>
</template>


<script>
export default {
  data(){
    return {
      users: [],
      error: '',
      userName:'',
      userName:'',
      userName:''
    }
  },
  methods: {
      sendData() {
        if(this.userName == ' ') {
          this.error = 'ne verno';
          return;
        } else if(this.userEmail == ' '){
          this.error = 'Email ne verno';
          return;
        } else if(this.userPass == ' '){
          this.error = 'Pasee ne verno';
          return;
        }

          this.error = '';

        this.users.push({
          name: this.userName,
          pass: this.userPass,
          email: this.userPass
        })
      }
  }
}
</script>



<style scoped>

</style>
