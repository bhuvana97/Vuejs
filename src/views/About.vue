<template>
  <div class="about">
    
<form  @submit="handleSubmit">
  <div class="container">
    <h1>Sign In</h1>
    <hr>

    
   

    <input type="username" required  placeholder="username" v-model="username" >
 <input type="password" required placeholder=" Password" v-model="password">
  

  

    <div class="clearfix">
     
      <button type="submit" class="signupbtn">SignIn</button>
    </div>
  </div>
</form>
  </div>
</template>


<script>
// @ is an alias to /src


// export default {
//   name: 'Home',
//   components: {
//     HelloWorld
//   }
// }



import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'About',
  data(){
    return{


   
      username:"",
      password:"",
      users:[],
    }

  },
  props: {
    msg: String
  },
  methods: {
    handleSubmit(e){

     
let user ={

  username:this.username,
  password:this.password
};


  console.log(user)
  
e.preventDefault()
      console.log(user)
  

if(this.username=="admin" && this.password=="admin")
{
    this.$router.push('/Dashoard');

}

      let lusers=localStorage.users;
  lusers= JSON.parse(lusers);
 
 let letndex=lusers.findIndex(user=>user.username===this.username);
 let letndex1=lusers.findIndex(user=>user.password===this.password);

//  alert(letindex)
 if(letndex>-1 && letndex1>-1 )
{
  alert("successfully logined")
  this.$router.push('/UserLogin');
}


else{
  alert("submitted")
}











// if (localStorage.getItem("users") === null) {
//   alert("no item exists")

//     alert("submited")
//      if(localStorage.users)
//      {
//        let lsusers=localStorage.users;
//        this.users=JSON.parse(lsusers);
//      }
// this.users.push(user);
// localStorage.setItem('users',JSON.stringify(this.users));


// }
// else{
//   alert("item exists in database")
//     let lusers=localStorage.users;
//   lusers= JSON.parse(lusers);

//  let index=lusers.findIndex(user=>user.firstname===this.firstname)
//  if(index>-1)
// {
//   alert("exists")
// }
// else
// {
//   alert("submited")
//      if(localStorage.users)
//      {
//        let lsusers=localStorage.users;
//        this.users=JSON.parse(lsusers);
//      }
// this.users.push(user);
// localStorage.setItem('users',JSON.stringify(this.users));
// }


// }

    
    }

  },
}










</script>
<style scoped>
* {box-sizing: border-box}

  input[type=email], input[type=password] {
  width: 100%;
  padding: 15px;
  margin: 5px 0 22px 0;
  display: inline-block;
  border: none;
  background: #f1f1f1;
}
  input[type=username] {
  width: 100%;
  padding: 15px;
  margin: 5px 0 22px 0;
  display: inline-block;
  border: none;
  background: #f1f1f1;
}
input[type=email]:focus, input[type=password]:focus,input[type=username]:focus  {
  background-color: #ddd;
  outline: none;
}

hr {
  border: 1px solid #f1f1f1;
  margin-bottom: 25px;
}

/* Set a style for all buttons */
button {
  background-color: #04AA6D;
  color: white;
  padding: 14px 20px;
  margin: 8px 0;
  border: none;
  cursor: pointer;
  width: 100%;
  opacity: 0.9;
  border-radius: 20px;
}

button:hover {
  opacity:1;
}



 .signupbtn {
  float: middle;
  width: 50%;
}

.container {
  padding: 16px;
}

.clearfix::after {
  content: "";
  clear: both;
  display: table;
}

@media screen and (max-width: 300px) {
  .cancelbtn, .signupbtn {
    width: 100%;
  }
}
</style>