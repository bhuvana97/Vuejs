<template>
  <div class="about">
        <button @click="handleSubmit">logout</button>

<h3> Dashboard</h3>

welcome...


  <!-- <ul v-if="item" in users>
  </ul> -->
<table border="1px">
  <tr>
    






   <li v-for="title in users" :key="title.id">{{users}}</li>






    <!-- <td>
     
      email
    </td>
    <td>
      username
      </td>
      <td>
        password
        </td> -->
    </tr>

</table>

    

<!-- 
        <div className="title">
            {projects.map((data, key)=>{
                    console.log(key);
                return(
                    <div key={key}>
                    {data.email}
                    </div>
                );
            })} 
        </div> -->




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

// import Vue from 'vue'
import axios from 'axios'

// import VueAxios from 'vue-axios'
// Vue.use(VueAxios, axios)
export default {
  name: 'Dashoard',
  props: {
    msg: String
  },
  data()
  {
return{

  
  list:undefined}
  
  },
    methods: {
    log(keys) {
      

      console.log(keys)

    }
  },
  mounted(){






   var values = [],
        keys = Object.values(localStorage),
        i = keys.length;

    while ( i-- ) {
        values.push( localStorage.getItem(keys[i]) );
    }
localStorage.getItem("users");

    console.log("logged",keys)
console.log(users)




//   let  local = localStorage;
// for (var key in local) {
//   console.log(key);
// //Do something with key, access value by local[key]
// }
// axios.get("http://localhost:3000/posts")
// .then((resp)=>{
//   this.list=resp.data;
//   console.warn(resp.data)
// })
  },







  methods: {
    handleSubmit(){
      localStorage.clear();
      alert("successfully logout")
        this.$router.push('/about');
      // location.replace("http://127.0.0.1:8081/")   
    },
  },
}










</script>
<style scoped>

</style>