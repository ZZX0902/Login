<template>
  <div>
    <input type="text" v-model="loginForm.username" placeholder="用户名"/>
    <input type="text" v-model="loginForm.password" placeholder="密码"/>
    <button @click="login">登录</button>
  </div></template>

<script>

  export default {
  name: 'HelloWorld',
  data () {
    return {
      loginForm: {
        username: '',
        password: ''
      }
    }
  },
  // methods:{
  //   login:function () {
  //       axios.get("https://jsonplaceholder.typicode.com/posts", {
  //
  //       })
  //         .then(function (data) {
  //           console.log(data)
  //         });
  //
  //   }
  //


  //
    methods:{
    login:function () {
      this.$axios({
        method:'post',
        url:'https://jsonplaceholder.typicode.com/posts',
        data:this.qs.stringify({
          userId:this.loginForm.username,
          title:this.loginForm.password,
        })
      }).then((response) =>{
        console.log(response.data.title)
      }).catch((error) =>{
        console.log(error)
      })
    }
    },
    created(){

    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
