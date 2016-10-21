<template>
  <div id="one">
    用户名：<input type="text" v-model="username">
    密码：<input type="text" v-model="password">
    <button @click="login">登录</button>
  </div>
</template>

<script>
 	export default {
 		data(){
 			return{
 				username:"",
        password:""
 			}
 		},
    events:{
      "abc":function(msg){
        console.log(msg);
      }
    },
    props:["pmsg"],
 		methods:{
 			login:function(){
        
        // alert(this.pmsg)
        this.$emit("cev","11111111111111111111111")
        this.$dispatch("childev","child message")
        this.$http.get("static/user.json")
        .then(function(res){
          var username = res.body.username;
          var password = res.body.password;
          if(this.username==username && this.password==password){
           this.$router.go("/home")
           // console.log($router)
          }
        })
 				if(this.username=="abc" && this.password=="123"){
          this.$router.go("/home")
        }
 			}
 		}
 	}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
#one{
	width: 100%;
	height: 100%;
	color: #fff;
	background:#42b983;
}
</style>
