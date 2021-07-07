<template>
  <div class="home">
    <HelloWorld/>



<!-- <form  @submit="handleSubmit"> -->
  <div class="container">
    <h1>Sign Up</h1>
    <hr>

    
    <input type="email" required placeholder=" Email" v-model="email" >

    <input type="username" required  placeholder="username" v-model="username" >
 <input type="password" required placeholder=" Password" v-model="password">
  

    <div class="clearfix">
     
      <button v-on:click="handleSubmit" class="signupbtn">Sign Up</button>
    </div>
  <!-- </div>
</form> -->


  </div>

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
import axios from "axios"



export default {
  name: 'Home',
  data(){
    return{


      email:"",
      username:"",
      password:"",
      users:[],
    }

  },
  props: {
    msg: String
  },
  methods: {
    async handleSubmit(e){













let user ={
  email:this.email,
  username:this.username,
  password:this.password
};
  console.log(user)
  
e.preventDefault()
      console.log(user)
  


if (localStorage.users==null) {

   alert("submited")
     if(localStorage.users)
     {
       let lsusers=localStorage.users;
       this.users=JSON.parse(lsusers);
     }
this.users.push(user);
localStorage.setItem('users',JSON.stringify(this.users));
}

else{
  let lusers=localStorage.users;
  lusers= JSON.parse(lusers);
 
 let letndex=lusers.findIndex(user=>user.email===this.email)
//  alert(letindex)
 if(letndex>-1)
{
  alert(" already exists")
}













else{



   alert("submited")
     if(localStorage.users)
     {
       let lsusers=localStorage.users;
       this.users=JSON.parse(lsusers);
     }
this.users.push(user);
localStorage.setItem('users',JSON.stringify(this.users));


}

}








console.log("signup",this.email)
  //    let result = await axios.post("http://localhost:3000/posts",{

  // email:this.email,
  // username:this.username,
  // password:this.password

  //    })
  //    console.warn(result)
  //    if(result.status==201){
  //      localStorage.setItem("user-info",JSON.stringify(result.data))
  //    }
// let user ={
//   email:this.email,
//   username:this.username,
//   password:this.password
// };
//   console.log(user)
  
// e.preventDefault()
//       console.log(user)
  


// if (localStorage.users==null) {

//    alert("submited")
//      if(localStorage.users)
//      {
//        let lsusers=localStorage.users;
//        this.users=JSON.parse(lsusers);
//      }
// this.users.push(user);
// localStorage.setItem('users',JSON.stringify(this.users));
// }

// else{
//   let lusers=localStorage.users;
//   lusers= JSON.parse(lusers);
 
//  let letndex=lusers.findIndex(user=>user.email===this.email)
// //  alert(letindex)
//  if(letndex>-1)
// {
//   alert(" already exists")
// }













// else{



//    alert("submited")
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























// export default {
//   name: 'Home',
//   data(){
//     return{


//       email:"",
//       username:"",
//       password:"",
//       users:[],
//     }

//   },
//   props: {
//     msg: String
//   },
//   methods: {
//     async handleSubmit(){

     
// let user = axios.post("http://localhost:8081/users", {
//   email:this.email,
//   username:this.username,
//   password:this.password
// });
//   console.log(user)
  
// e.preventDefault()
//       console.log(user)
  


// if (localStorage) {


//   let lusers=localStorage.users;
//   lusers= JSON.parse(lusers);
 
//  let letndex=lusers.findIndex(user=>user.email===this.email)
// //  alert(letindex)
//  if(letndex>-1)
// {
//   alert(" already exists")
// }













// else{



//    alert("submited")
//      if(localStorage.users)
//      {
//        let lsusers=localStorage.users;
//        this.users=JSON.parse(lsusers);
//      }
// this.users.push(user);
// // localStorage.setItem('users',JSON.stringify(this.users));

// localStorage.setItem('users',result.data);

// }

// }





// // if (localStorage.getItem("users") === null) {
// //   alert("no item exists")

// //     alert("submited")
// //      if(localStorage.users)
// //      {
// //        let lsusers=localStorage.users;
// //        this.users=JSON.parse(lsusers);
// //      }
// // this.users.push(user);
// // localStorage.setItem('users',JSON.stringify(this.users));


// // }
// // else{
// //   alert("item exists in database")
// //     let lusers=localStorage.users;
// //   lusers= JSON.parse(lusers);

// //  let index=lusers.findIndex(user=>user.firstname===this.firstname)
// //  if(index>-1)
// // {
// //   alert("exists")
// // }
// // else
// // {
// //   alert("submited")
// //      if(localStorage.users)
// //      {
// //        let lsusers=localStorage.users;
// //        this.users=JSON.parse(lsusers);
// //      }
// // this.users.push(user);
// // localStorage.setItem('users',JSON.stringify(this.users));
// // }


// // }

    
//     }

//   },
// }










</script>
<style scoped>
* {box-sizing: border-box}

/* Full-width input fields */
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
/* 
button:hover {
  opacity:1;
} */

/* Extra styles for the cancel button */
.cancelbtn {
  padding: 14px 20px;
  background-color: #f44336;
}

/* Float cancel and signup buttons and add an equal width */
.cancelbtn, .signupbtn {
  float: middle;
  width: 50%;
}

/* Add padding to container elements */
.container {
  padding: 16px;
}

/* Clear floats */
.clearfix::after {
  content: "";
  clear: both;
  display: table;
}

/* Change styles for cancel button and signup button on extra small screens */
@media screen and (max-width: 300px) {
  .cancelbtn, .signupbtn {
    width: 100%;
  }
}
</style>