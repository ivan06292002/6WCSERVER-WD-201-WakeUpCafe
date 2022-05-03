<style>
    body {
        background: url('white.jpg');
        background-repeat: no-repeat;
        background-size: 100%;
}
</style>
<template> 
    <div class="row justify-content-center">
        <div class="col-md-6">
            <h3 class="text-center "><i>ORDER FORM</i></h3>
            <form @submit.prevent="handleSubmitForm">
                <div class="form-group">
                   <label>Customer Name</label>
                    <input type="text" class="form-control" v-model="student.name" required>
                </div>
                <div class="form-group">
                    <label>Email</label>
                    <input type="email" class="form-control" v-model="student.email" required>
                </div>
                <div class="form-group">
                    <label>Phone Number</label>
                    <input type="text" class="form-control" v-model="student.phone" required>
                </div>
                <div class="form-group">
                    <label>Coffee</label>
                    <table>
                        <td><select class="input" name="student.coffee" v-model="student.coffee" required>
                            <option value="Hazel">Hazelnut</option>
                            <option value="French">French Vanilla</option>
                            <option value="Pumpkin">Pumpkin Spice</option>
                            <option value="Caramel">Caramel</option>
                        </select></td>
                    </table>
                   
                </div>
                <div class="form-group">
                   <label>Tea</label>
                     <table>
                        <td><select class="input" name="student.coffee" v-model="student.tea" required>
                            <option value="Butter">Butter Tea Blend</option>
                            <option value="Organic">Organic Earl Gray Cream Tea</option>
                            <option value="Thai">Thai Ginger Tea</option>
                            <option value="Egyptian">Egyptian Hibiscus Petal Tea</option>
                        </select></td>
                    </table>
                </div>
                <div class="form-group">
                    <br>
                    <button class="btn btn-danger btn-block">Submit</button>
                </div>
            </form>
        </div>
    </div>
</template>
<script>
    import axios from "axios";
    export default {
        data() {
            return {
                student: {
                   name: '',
                   email: '',
                   phone: '',
                   coffee: '',
                   tea: ''
                }
            }
        },
        methods: {
            handleSubmitForm() {
                let apiURL = 'http://localhost:4000/api/create-student';
                
                axios.post(apiURL, this.student).then(() => {
                  this.$router.push('/view')
                  this.student = {
                    name: '',
                    email: '',
                    phone: '',
                    coffee: '',
                    tea: ''
                  }
                }).catch(error => {
                    console.log(error)
                });
            }
        }
    }
</script>