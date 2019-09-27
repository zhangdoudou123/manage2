<template>
  <div class="add container">
    <form class="form-horizontal" role="form" @submit.prevent="addcustomers">
      <h4 class="page-header">用户信息</h4>
      <hr>
      <div class="form-group" >
        <label for="name">姓名</label>
        <div class="col-sm-10">
          <input type="text" class="form-control" id="name" placeholder="name" v-model="customers.name"/>
        </div>
      </div>
      <div class="form-group" >
        <label for="phone" class="col-sm-2 control-label">电话</label>
        <div class="col-sm-10">
          <input type="text" class="form-control" id="phone" placeholder="phone" v-model="customers.phone"/>
        </div>
      </div>
      <div class="form-group" >
        <label for="email" class="col-sm-2 control-label">邮箱</label>
        <div class="col-sm-10">
          <input type="text" class="form-control" id="email" placeholder="email" v-model="customers.email"/>
        </div>
      </div>
      <div class="form-group" >
        <label for="education" class="col-sm-2 control-label">学历</label>
        <div class="col-sm-10">
          <input type="text" class="form-control" id="education" placeholder="education" v-model="customers.education"/>
        </div>
      </div>
      <div class="form-group" >
        <label for="graduationschool" class="col-sm-2 control-label">毕业学校</label>
        <div class="col-sm-10">
          <input type="text" class="form-control" id="graduationschool" placeholder="graduationschool" v-model="customers.graduationschool"/>
        </div>
      </div>
      <div class="form-group" >
        <label for="professtion" class="col-sm-2 control-label">职业</label>
        <div class="col-sm-10">
          <input type="text" class="form-control" id="professtion" placeholder="professtion" v-model="customers.professtion"/>
        </div>
      </div>
      <div class="form-group" >
        <label for="profile" class="col-sm-2 control-label" >个人简介</label>
        <div class="col-sm-10">
          <input type="textarea" class="form-control" id="profile" style="height : 100px" v-model="customers.profile"/>
        </div>
      </div>

      <div class="form-group">
        
          <button type="submit" class="btn btn-primary">添加</button>
        
      </div>
    </form>
  </div>
</template>

<script>
export default {
  name: "add",
  props: {},
  data(){
    return{
      customers:[],
    }
  },
  methods:{
    addcustomers(){
     // alert(123);
      if(!this.customers.name || !this.customers.phone || !this.customers.email){
        alert("请添加对应信息");
      }else {
        let newCustomers  = {
          name : this.customers.name,
          phone : this.customers.phone,
          email : this.customers.email

        }
        this.$http.post("http://localhost:3000/users",newCustomers)
        .then(function(){
          //window.console.log(response);
         // window.console.log("添加用户成功！");
          this.$router.push({path : "/",query:{aler :"添加用户成功！"}});
        })
      }
    }
  }
};
</script>

<style scoped>
.page-header {
  text-align: left;
  margin-top: 20px;
  color: aqua;
}
</style>
