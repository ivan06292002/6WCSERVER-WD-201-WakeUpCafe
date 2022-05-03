<template> 
    <div class="row justify-content-center">
        <div class="col-md-6">
            <form @submit.prevent="handleSubmitForm">
                <div class="content">
            <h1>COFFEE MENU</h1>
            <br>
            <br>
            <h2><b>Hazelnut</b></h2>
            <br>---------------------------------------------------------------------------------------------------
            <br>
            <br>
            <h5>Hazelnut has a sweet, buttery taste with a distinctive nutty and enticing aroma that you simply can’t ignore. It blends nicely with vanilla and chocolate, so you’ll likely find it commonly paired with these in drinks. The nutty taste of coffee beans works so well with hazelnut. And while the flavor is strong and enticing, it provides a rather mild and smooth drinking experience.You’ll find hazelnut in plenty of different options due to the popularity of the blend. So, regardless of your taste preference, you’re sure to find something that suits your palates.</h5>
            
           <br>
            <h2><b>French Vanilla</b></h2>
            <br>---------------------------------------------------------------------------------------------------
            <br>
            <br>
            <h5>French Vanilla is, by far, the most popular coffee flavor available. You simply can’t go wrong with vanilla’s sweet aroma and rich taste when it comes to flavoring just about anything. Vanilla is subtle and almost comforting. That’s why it can easily overwhelm most bold tastes. These qualities make vanilla a brilliant complement to coffee’s typical stronger and robust flavor. For best results, consider using vanilla with medium or light roast coffee beans. You want to add French vanilla to your coffee, though, and not just plain vanilla. That’s because the former is more caramelized and has a deeper flavor than the latter owing to its production process. Thanks to the popularity of French vanilla, you can easily find the flavor in a wide variety of products, such as creamers, k-cups, instant coffees. Regardless of how you like your coffee – standard black, lattes, cappuccino, or macchiato – a few drops of French vanilla will enhance the flavor.And if you want something incredibly tasty, try adding vanilla to your coffee beans the night before. Brew your coffee the next morning and enjoy the best-tasting vanilla-flavored cup of coffee you’ve ever had!</h5>
            
           
            ________________________________________________________________________________________________
            
            <br>
            <br>
            <h2><b>Pumpkin Spice</b></h2>
            <br>---------------------------------------------------------------------------------------------------
            <br>
            <br>
            <h5>Pumpkin spice is another brilliant seasonal blend. It is the go-to choice for many coffee drinkers, especially during the chilly fall evenings. Typically, it’s a fine blend of autumn spices, including nutmeg, cinnamon, ginger, and cloves. Pumpkin spice is highly irresistible when added to good-quality coffee. You can wait until the leaves start to change color before heading to coffee shops and grappling with the price tag of a pumpkin spice latte. Or, you can choose to celebrate fall by preparing your own homemade pumpkin-flavored coffee using natural ingredients. Ultimately, it’s your call. But we’ll suggest you skip the calories and make your pumpkin spice latte yourself.</h5>
            
           
            ________________________________________________________________________________________________
            
            <br>
            <br>
            <h2><b>Caramel</b></h2>
            <br>---------------------------------------------------------------------------------------------------
            <br>
            <br>
            <h5>Caramel has a strong, robust, and smooth taste profile. Yet, it is sweet and quite agreeable. All of these combine to provide a rich and satisfying experience when added to coffee. The buttery sweetness of caramel is hard to resist, making it a great way to spice up your coffee! In fact, you can drink your coffee with or without milk as long as you add caramel. That’s because the flavor works so well with coffee, there’s usually no need to add milk. The toasted hints of the beans complement caramel’s syrupy sweetness to make a great tasting homemade caramel macchiato.</h5>
            
           
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
                  this.$router.push('/coffee')
                
                }).catch(error => {
                    console.log(error)
                });
            }
        }
    }
</script>