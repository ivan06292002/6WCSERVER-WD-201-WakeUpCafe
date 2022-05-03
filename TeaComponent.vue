<template> 
    <div class="row justify-content-center">
        <div class="col-md-6">
            <form @submit.prevent="handleSubmitForm">
                <div class="content">
            <h1>TEA MENU</h1>
            <br>
            <br>
            <h2><b>Butter Tea Blend</b></h2>
            <br>---------------------------------------------------------------------------------------------------
            <br>
            <br>
            <h5>Our Butter Tea Blend was inspired by Tim Ferriss who famously replaced his morning coffee with a blend of different types of tea. This blend includes a mixture of sencha green tea, young pu-erh tea, and Brazilian green yerba mate tea resulting in a delightfully rich tea that rivals the flavors of a cup of coffee. Brew this tea and enjoy it on its own or mix it with MCT oil, grass-fed butter or heavy cream to draw out the rich flavor profile. This tea will also give you a longer-lasting energy boost without the jitters and crashes associated with coffee.</h5>
            
           <br>
            <h2><b>Organic Earl Grey Cream Tea</b></h2>
            <br>---------------------------------------------------------------------------------------------------
            <br>
            <br>
            <h5>This organic tea offers a delicious new take on the classic flavors of Earl Grey tea. Normal Earl Grey tea contains a blend of black tea leaves and rinds of bergamot oranges.  This blend features those ingredients plus the addition of dried vanilla to create a smooth and creamy texture that is delightful. This organic tea is similar to English Breakfast teas with bold notes of earthy and roasted flavors thanks to the black tea leaves. It's also a bit more vibrant than traditional breakfast teas thanks to the citrusy notes of the bergamot and the smooth, rich hints of the vanilla. This tea also boasts a moderate amount of caffeine so it's the perfect way to start the day or add an extra boost to the afternoon.</h5>
            
           
            ________________________________________________________________________________________________
            
            <br>
            <br>
            <h2><b>Thai Ginger Tea</b></h2>
            <br>---------------------------------------------------------------------------------------------------
            <br>
            <br>
            <h5>Ginger tea is made from the root of the ginger plant. The tea stands out from other herbal teas thanks to its mildly spicy notes and warming sensation. Our ginger tea is sourced from Sing Buri in Thailand and is best brewed with a touch of lemon and a dash of honey. These ingredients add a tangy note while drawing out the heat of the ginger pieces. The tea is also well-known for its digestive benefits as it may help to soothe nausea, upset stomach, and streamline digestion.</h5>
            
           
            ________________________________________________________________________________________________
            
            <br>
            <br>
            <h2><b>Egyptian Hibiscus Petal Tea</b></h2>
            <br>---------------------------------------------------------------------------------------------------
            <br>
            <br>
            <h5>Hibiscus tea is a wildly popular beverage in the Caribbean and Central America. The beverage is known by other names including agua de Jamaica, roselle, and sorrel. The tea features a fruity flavor that is ideal for hot and iced teas. When brewed as an iced tea, it offers an almost lemonade-like flavor that is refreshing and invigorating. The tea is also stunning with a deep magenta hue that is similar to grenadine. This particular herbal tea has high amounts of vitamin C and vitamin A. Simply add the flower petals to a cup of hot water and enjoy the vibrant flavors and colors with each sip. </h5>
            
           
            ________________________________________________________________________________________________
            
         
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
                  this.$router.push('/tea')
                
                }).catch(error => {
                    console.log(error)
                });
            }
        }
    }
</script>