<template>
    <div class="container mt-5" >
        <div class="row" >
          <div class="col-md-12" >
            <div class="card">
              <div class="card-header">
                <h3 class="card-title">User Table</h3>

                <div class="card-tools">
                    <button class="btn btn-success" data-toggle="modal"
                             data-target="#addNewUser" type="button">
                        Add New
                         <i class="fa fa-user-plus text-white"></i>
                    </button>
                </div>

                
              </div>
              <!-- /.card-header -->
              <div class="card-body table-responsive p-0">
                <table class="table table-hover">
                  <tbody><tr>
                    <th>ID</th>
                    <th>Name</th>
                    <th>Email</th>
                    <th>Type</th>
                    <th>Modify</th>
                  </tr>
                  <tr>
                    <td>183</td>
                    <td>John Doe</td>
                    <td>11-7-2014</td>
                    <td><span class="tag tag-success">Approved</span></td>
                    <td>
                        <a href="#">
                            <i class="fa fa-pencil text-indigo" aria-hidden="true"></i>
                        </a>
                        /
                        <a href="#">
                            <i class="fa fa-trash text-red" aria-hidden="true"></i>
                        </a>
                    </td>
                  </tr>
                 
                </tbody></table>
              </div>
              <!-- /.card-body -->
            </div>
            <!-- /.card -->
          </div>
        </div>




        <!-- Modal -->
        <div class="modal fade" id="addNewUser" tabindex="-1" role="dialog" aria-labelledby="addNewUserLabel" aria-hidden="true">
          <div class="modal-dialog modal-dialog-centered" role="document">
            <div class="modal-content">
              <div class="modal-header">
                <h5 class="modal-title" id="addNewUserLabel">Add New</h5>
                <button type="button" class="close" data-dismiss="modal" aria-label="Close">
                  <span aria-hidden="true">&times;</span>
                </button>
              </div>
              <div class="modal-body">
                
                <div class="form-group">
                     <input v-model="form.name" type="text" name="name" placeholder="Enter Name" 
                       class="form-control" :class="{ 'is-invalid': form.errors.has('name') }">
                     <has-error :form="form" field="name"></has-error>
                </div>
                <div class="form-group">
                     <input v-model="form.email" type="text" name="email" placeholder="Email Address" 
                       class="form-control" :class="{ 'is-invalid': form.errors.has('email') }">
                     <has-error :form="form" field="email"></has-error>
                </div>
                 <div class="form-group">
                     <textarea v-model="form.bio" name="bio" placeholder="Bio" 
                       class="form-control" :class="{ 'is-invalid': form.errors.has('bio') }">
                   </textarea>
                     <has-error :form="form" field="bio"></has-error>
                </div>

                <div class="form-group">
                    <select name="type" id="type" v-model="form.type"  class="form-control" :class="{ 'is-invalid': form.errors.has('type') }">
                        <option value="">Select User Role</option>
                        <option value="admin">Admin</option>
                        <option value="user">User</option>
                        <option value="author">Author</option>
                    </select>
                     <has-error :form="form" field="email"></has-error>
                </div>

                 <div class="form-group">
                     <input v-model="form.password" type="password" name="password" placeholder="Password" 
                       class="form-control" :class="{ 'is-invalid': form.errors.has('password') }">
                     <has-error :form="form" field="password"></has-error>
                </div>
               


              </div>
              <div class="modal-footer">
                <button type="button" class="btn btn-secondary" data-dismiss="modal">Close</button>
                <button type="button" class="btn btn-primary">Create</button>
              </div>
            </div>
          </div>
        </div>
        <!-- modal end -->

    </div>
    <!-- container end -->
</template>

<script>
    export default {
        data(){
            return{
                form : new Form({
                    name : '' ,
                    email : '' ,
                    password : '' ,
                    type : '' ,
                    bio : '' ,
                    photo : '' ,
                    name : '' 
                })
            }
        },
        mounted() {
            console.log('Component mounted.')
        }
    }
</script>
