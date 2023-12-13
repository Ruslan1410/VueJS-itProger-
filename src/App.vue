<template>
    <input type ="text" v-model="userName" placeholder="Имя">
    <input type ="password" v-model="userPass" placeholder = "Пароль">
    <input type ="email" v-model="userEmail" placeholder = "Email">
    <p className="error">{{ error }}</p>
    <button @click ="sendData()">Отправить</button>
    
    <div v-if="users.length == 0" className="user">
      у нас нет пользователей
    </div>
    <div v-else-if="users.length == 1" className="user">
     users has 1 element
    </div>
    <div v-else className="user">
      users has more than 1 element
    </div>
    <div v-for="(el, index) in users" :key="index" className="user">
      <h3>{{  el.name }}</h3>
      <p>{{ el.email }} - <b>{{ el.pass }}</b></p>
    </div>
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
