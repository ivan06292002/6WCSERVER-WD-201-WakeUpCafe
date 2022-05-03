<template>
    <div class="row justify-content-center">
        <div class="col-md-6">
            <h3 class="text-center">Update Student</h3>
            <form @submit.prevent="handleUpdateForm">
                <div class="form-group">
                    <label>Name</label>
                    <input type="text" class="form-control" v-model="student.name" required>
                </div>
                <div class="form-group">
                    <label>Email</label>
                    <input type="email" class="form-control" v-model="student.email" required>
                </div>
                <div class="form-group">
                    <label>Phone</label>
                    <input type="text" class="form-control" v-model="student.phone" required>
                </div>
                <div class="form-group">
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
                            <option value="Organic">Organic Earl Grey Cream Tea</option>
                            <option value="Thai">Thai Ginger Tea</option>
                            <option value="Egyptian">Egyptian Hibiscus Petal Tea</option>
                        </select></td>
                    </table>
                </div>
                    <br>
                    <button class="btn btn-danger btn-block">Update</button>
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
            student: { }
        }
    },
    created() {
        let apiURL = `http://localhost:4000/api/edit-student/${this.$route.params.id}`;
        axios.get(apiURL).then((res) => {
            this.student = res.data;
        })
    },
    methods: {
        handleUpdateForm() {
            let apiURL = `http://localhost:4000/api/update-student/${this.$route.params.id}`;
            axios.put(apiURL, this.student).then((res) => {
                console.log(res)
                this.$router.push('/view')
            }).catch(error => {
                console.log(error)
            });
        }
    }
}
</script>