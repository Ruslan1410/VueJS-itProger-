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
    <User v-for="(el, index) in users" :key="index" :user="el" :index="index" :deleteUser="deleteUser"/>
   
</template>


<script>
import User from './components/User.vue'

export default {
  components: { User },
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
      },
      deleteUser(index){
        this.users.splice(index, 1);
      }
  }
}
</script>



<style scoped>

</style>
