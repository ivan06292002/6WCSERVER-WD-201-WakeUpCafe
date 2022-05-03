<template>
    <div class="row">
        <div class="col-md-12">
            <table class="table table-striped">
                <thead class="thead-dark">
                    <tr>
                       <th><p style="color:white">Name</p></th>
                        <th><th><p style="color:white">Email</p></th>
                        <th><th><p style="color:white">Phone Number</p></th>
                        <th><th><p style="color:white">Coffee</p></th>
                        <th><th><p style="color:white">Teas</p></th>
                    </tr>
                </thead>
                <tbody>
                    <tr v-for="student in Students" :key="student._id">
                        <td>{{ student.name }}</td>
                        <td>{{ student.email }}</td>
                        <td>{{ student.phone }}</td>
                        <td>{{ student.coffee }}</td>
                        <td>{{ student.tea }}</td>
                        <td>
                            <router-link :to="{name: 'edit', params: { id: student._id }}" class="btn btn-success">Edit
                            </router-link>
                            <button @click.prevent="deleteStudent(student._id)" class="btn btn-danger">Delete</button>
                        </td>
                    </tr>
                </tbody>
            </table>
        </div>
    </div>
</template>
<script>
    import axios from "axios";
    export default {
        data() {
            return {
                Students: []
            }
        },
        created() {
            let apiURL = 'http://localhost:4000/api';
            axios.get(apiURL).then(res => {
                this.Students = res.data;
            }).catch(error => {
                console.log(error)
            });
        },
        methods: {
            deleteStudent(id){
                let apiURL = `http://localhost:4000/api/delete-student/${id}`;
                let indexOfArrayItem = this.Students.findIndex(i => i._id === id);
                if (window.confirm("Do you really want to delete?")) {
                    axios.delete(apiURL).then(() => {
                        this.Students.splice(indexOfArrayItem, 1);
                    }).catch(error => {
                        console.log(error)
                    });
                }
            }
        }
    }
</script>
<style>
    .btn-success {
        margin-right: 10px;
    }
</style>