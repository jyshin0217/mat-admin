<template>
  <form class="loginForm" @submit.prevent="sendPost">
      <h2>Login</h2>
      <div class="idForm">
        <input type="text" class="id" placeholder="ID" v-model="id">
      </div>
      <div class="passForm">
        <input type="password" class="pw" placeholder="PW" v-model="pw">
      </div>
      <button type="button" class="btn" @click="buttonPost">
        LOG IN
      </button>
      
      <div class="bottomText">
        Don't you have ID? <a href="#">sign up</a>
      </div>
    </form>
</template>

<script>
export default {
    data() {
        return {
            id: "",
            pw: ""
        }
    },
    methods: {
        sendPost() {
            console.log('sendPost')
        },
        buttonPost(){
            console.log('button test')
            console.log('id => ' + this.id)
            console.log('pw => ' + this.pw)
            if(this.id !== '' && this.pw !== '') {
                this.$router.push({ path: '/home' })
            }
        }
    }
}
</script>

<style>
*{
  margin: 0px;
  padding: 0px;
  text-decoration: none;
  font-family:sans-serif;

}

body {
  background-image: #34495e;
}

.loginForm {
  position:absolute;
  width:300px;
  height:400px;
  padding: 30px, 20px;
  background-color:#FFFFFF;
  text-align:center;
  top:40%;
  left:50%;
  transform: translate(-50%,-50%);
  border-radius: 15px;
}

.loginForm h2{
  text-align: center;
  margin: 30px;
}

.idForm{
  border-bottom: 2px solid #adadad;
  margin: 30px;
  padding: 10px 10px;
}

.passForm{
  border-bottom: 2px solid #adadad;
  margin: 30px;
  padding: 10px 10px;
}

.id {
  width: 100%;
  border:none;
  outline:none;
  color: #636e72;
  font-size:16px;
  height:25px;
  background: none;
}

.pw {
  width: 100%;
  border:none;
  outline:none;
  color: #636e72;
  font-size:16px;
  height:25px;
  background: none;
}

.btn {
  position:relative;
  left:40%;
  transform: translateX(-50%);
  margin-bottom: 40px;
  width:80%;
  height:40px;
  background: linear-gradient(125deg,#81ecec,#6c5ce7,#81ecec);
  background-position: left;
  background-size: 200%;
  color:white;
  font-weight: bold;
  border:none;
  cursor:pointer;
  transition: 0.4s;
  display:inline;
}

.btn:hover {
  background-position: right;
}

.bottomText {
  text-align: center;
}
</style>