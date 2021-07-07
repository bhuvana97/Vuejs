<template>
  <div>
<button @click="handleSubmit">logout</button>

<h2>welcome... user</h2>
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





export default {
  name: 'UserLogin',
  props: {
    msg: String
  },
  methods: {
    handleSubmit(){
      localStorage.clear();
      alert("successfully logout")
        this.$router.push('/about');
      // location.replace("http://127.0.0.1:8081/")   
    }
},
}
</script>








