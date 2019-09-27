<template>
  <div class="customers">
    <Alert v-if="aler" :message = "aler"></Alert>
    <table class="table table-striped">
      <thead>
        <tr>
          <th>姓名</th>
          <th>电话</th>
          <th>邮箱</th>
          <th></th>
        </tr>
      </thead>
      <tbody>
        <tr v-for = "cus in customers" :key="cus">
          <td>{{cus.name}}</td>
          <td>{{cus.phone}}</td>
          <td>{{cus.email}}</td>
          <td><router-link to="/customers" class="btn">详细</router-link></td>
        </tr>
      </tbody>
    </table>
    
  </div>
</template>

<script>
import Alert from "../components/Alert.vue"
export default {
  name: 'customers',
  data(){
    return {
      customers:[],
      aler : ""
    }
  },
  components:{
    Alert,

  },
  methods:{
    fetchCustomers(){
      this.$http.get("http://localhost:3000/users")
      .then(function(response){
       //alert(response);
      this.customers = response.body;
      })
    }
    },
    created(){
      if(this.$route.query.aler){
        this.aler = this.$route.query.aler;
      }
      this.fetchCustomers();
    },
    updated(){
      this.fetchCustomers();
    }
}
</script>
