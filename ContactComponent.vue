<template> 
    <div class="row justify-content-center">
        <div class="col-md-6">
            <form @submit.prevent="handleSubmitForm">
                <div class="content">
            <h1>WAKE UP CAFE
              <br><span>Contact </span>Information</h1>
            <br>
            <br>
            <p class="par"><b>Aquino, ElaGail </b>
            <br>----------------------------------------------------
            <br>
            Email address: egaquino@student.hau.edu.ph<br>
            Contact # : 0912-999-4598
            <br>
            ___________________________________________________
            </p>

            <p class="par"><b>Dayrit, Carl Ivan P.</b>
            <br>----------------------------------------------------
            <br>
            Email address: cpdayrit@student.hau.edu.ph<br>
            Contact # : 0997-331-2221
            <br>
             ___________________________________________________
            </p>

            <p class="par"><b>Galupe, Raymond</b>
            <br>----------------------------------------------------
            <br>
            Email address: rpgalupe@student.hau.edu.ph
            <br>
            Contact # : 0908-495-3652
            <br>
            ___________________________________________________
            </p>

             <p class="par"><b>Gegante, Carl</b>
            <br>----------------------------------------------------
            <br>
            Email address: cdgegante@student.hau.edu.ph
            <br>
            Contact # : 0921-976-8959
            <br>
            ___________________________________________________
            </p>

             <p class="par"><b>Guilas, Felino</b>
            <br>----------------------------------------------------
            <br>
            Email address: fdrguilas@gmail.com
            <br>
            Contact # : 0975-504-0837
            <br>
            ___________________________________________________
            </p>

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
                
            }
        },
        methods: {
            handleSubmitForm() {
                let apiURL = 'http://localhost:4000/api/create-student';
                
                axios.post(apiURL, this.student).then(() => {
                  this.$router.push('/coffee')
                
                }).catch(error => {
                    console.log(error)
                });
            }
        }
    }
</script>