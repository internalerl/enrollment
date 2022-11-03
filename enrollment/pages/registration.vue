<template>
<section style="background-color: #6b8f71;">
  <div>

    <nav class="navbar justify-content-center navbar-expand-lg navbar-light" style="background-color: #466362;">
        <a class="navbar-brand" href="#">Plantacy</a>
          <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarNavAltMarkup" aria-controls="navbarNavAltMarkup" aria-expanded="false" aria-label="Toggle navigation">
            <span class="navbar-toggler-icon"></span>
          </button>
        <div id="navbarNavAltMarkup" class="collapse navbar-collapse" >
          <div class="navbar-nav">
            <a class="nav-item nav-link" href="/IndexPage">Home</a>
            <a class="nav-item nav-link" href="/dashboard">Dashboard</a>
            <a class="nav-item nav-link" href="/order">Orders</a>
            <a class="nav-item nav-link" href="/product">Product</a>
            <a class="nav-item nav-link" href="/customers">Customers</a>
         </div>
        </div>
    </nav>
  <div class="container">
    <br>
    <div class="form-inline" action="#">
    <input type="text" id="form-name" v-model="item.Fname" placeholder="First Name" class="form-control">
    <input type="text" id="form-name" v-model="item.Lname" placeholder="Last Name" class="form-control">
    <input type="text" id="form-name" v-model="item.address" placeholder="Address" class="form-control">
    <input type="number" v-model="item.contactnumber" placeholder="Contact Number" class="form-control" v-on:keyup.enter="addItem">
    <button @click="addItem" class="btn btn-dark"><i class="fas fa-plus">+</i></button>
    </div>
      
    <br><br>
    <table class="table table-striped table-bordered table-sm">
      <thead class="thead-light">
        <th>First Name</th>
        <th>Last Name</th>
        <th>Address</th>
        <th>Contact Num</th>
        <th class="col-2">Edit/Delete</th>
      </thead>
      <tr v-for="item in items" :key="item.name">
        <td>
          <input v-if="item.edit" type="text" v-model="item.Fname"  v-on:keyup.enter="item.edit = !item.edit">
          <span v-else>{{item.Fname}} </span>
        </td>
        <td>
          <input v-if="item.edit" type="text" v-model="item.Lname" v-on:keyup.enter="item.edit = !item.edit">
          <span v-else>{{item.Lname}} </span>
        </td>
        <td>
          <input v-if="item.edit" type="text" v-model="item.address" v-on:keyup.enter="item.edit = !item.edit">
          <span v-else>{{item.address}} </span>
        </td>
        <td>
          <input v-if="item.edit" type="text" v-model="item.contactnumber" v-on:keyup.enter="item.edit = !item.edit">
          <span v-else>{{item.contactnumber}} </span>
        </td>
        <td><button @click="item.edit = !item.edit" class="btn btn-info"><i class="far fa-edit">Edit</i></button>
          <button @click="removeItem(index)" class="btn btn-danger"><i class="far fa-trash-alt">Delete</i></button></td>
      </tr>
    </table>
</div>
</div>
</section>
</template>

<script scope>

  export default {
    data() {
    return {
      item: {Fname: "",  Lname: "", address: "", contactnumber: "",  edit: false},
      items: []
    }
  },
  methods:{
    addItem() {
      this.items.push({
        Fname:this.item.Fname, Lname:this.item.Lname, address:this.item.address, contactnumber:this.item.contactnumber, edit: false}
        );
      this.item = [];
    },
    removeItem(index){
      this.items.splice(index, 1)
    }
  }
  }
</script>

<style scoped>
.form-inline input {
  margin-right:8px;
}
</style>
