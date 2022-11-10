<template>
<section style="background-color: #6b8f71;">
  <div>
    <NavBar />
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
        <th style="background-color: #c2a878;">First Name</th>
        <th style="background-color: #c2a878;">Last Name</th>
        <th style="background-color: #c2a878;">Address</th>
        <th style="background-color: #c2a878;">Contact Num</th>
        <th class="col-2" style="background-color: #c2a878;">Edit/Delete</th>
      </thead>
      <tr v-for="item in items" :key="item.name">
        <td style="background-color: #fcf300;">
          <input v-if="item.edit" type="text" v-model="item.Fname"  v-on:keyup.enter="item.edit = !item.edit">
          <span v-else>{{item.Fname}} </span>
        </td>
        <td style="background-color: #fcf300;">
          <input v-if="item.edit" type="text" v-model="item.Lname" v-on:keyup.enter="item.edit = !item.edit">
          <span v-else>{{item.Lname}} </span>
        </td>
        <td style="background-color: #fcf300;">
          <input v-if="item.edit" type="text" v-model="item.address" v-on:keyup.enter="item.edit = !item.edit">
          <span v-else>{{item.address}} </span>
        </td>
        <td style="background-color: #fcf300;">
          <input v-if="item.edit" type="text" v-model="item.contactnumber" v-on:keyup.enter="item.edit = !item.edit">
          <span v-else>{{item.contactnumber}} </span>
        </td>
        <td style="background-color: #fcf300;"><button @click="item.edit = !item.edit" class="btn btn-info"><i class="far fa-edit">Edit</i></button>
          <button @click="removeItem(index)" class="btn btn-danger"><i class="far fa-trash-alt">Delete</i></button></td>
      </tr>
    </table>
</div>
</div>
</section>
</template>

<script scope>

  import NavBar from "~/components/NavBar.vue"
  export default {
    name: 'RegisTer',
    components: {NavBar,},
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
