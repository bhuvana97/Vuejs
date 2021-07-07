<template>
  <div>
<button @click="handleSubmit">logout</button>

<h2>welcome... user</h2>
  </div>
</template>


<script>





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
     
    }
},
}
</script>








