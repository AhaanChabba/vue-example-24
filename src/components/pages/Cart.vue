
<script>
import Cartitem from "../widgets/Cartitem.vue";
export default {
    data() {
        return {
         
            Cartlist: [
                {
                    imageUrl: "https://static.nike.com/a/images/t_PDP_864_v1/f_auto,b_rgb:f5f5f5/243972ca-dba9-4f9c-af56-285c46ce3bed/phantom-gx-2-elite-ag-low-top-soccer-cleats-RVpzb1.png",
                    productname: "Nike Phantom GX 2 Elite AG Low-Top Soccer Cleats",
                    productDesc: "Obsessed with perfecting your craft? We made this for you. In the middle of the storm, with chaos swirling all around you, you’ve calmly found the final third of the field, thanks to your uncanny mix of on-ball guile and grace. Go finish the job in the Phantom GX 2 Elite. Revolutionary Nike Gripknit covers the striking area of the cleat while Nike Cyclone 360 traction helps guide your unscripted agility. We design Elite cleats for you and the world’s biggest stars to give you high-level quality, because you demand greatness from yourself and your footwear.",
                    productprice: "$260"


                },

                {
                    imageUrl: "https://static.nike.com/a/images/t_PDP_864_v1/f_auto,b_rgb:f5f5f5/9deeaf7a-4384-4457-aa57-42161161b13d/usmnt-2023-match-home-mens-dri-fit-adv-soccer-jersey-Jrb4c1.png",
                    productname: "USMNT 2023 Match Home Men's Nike Dri-FIT ADV Soccer Jersey",
                    productDesc: "Our Match collection pairs authentic design details with lightweight, quick-drying technology to help keep the world's biggest soccer stars cool and comfortable on the field.",
                    productprice: "$170"
                },

                {
                    imageUrl: "https://static.nike.com/a/images/t_PDP_1280_v1/f_auto,b_rgb:f5f5f5/2638aa08-c410-4cd8-abe9-254706100451/premier-league-flight-soccer-ball-dM9sq5.png",
                    productname: "Premier League Flight Soccer Ball",
                    productDesc: "Meet the ball made to withstand it all. Molded grooves for less drag, a grippy texture for control in any weather—all built in so you can excel on the pitch every time you play.",
                    productprice: "$167"
                },

                {
                    imageUrl: "https://static.nike.com/a/images/t_PDP_1280_v1/f_auto,b_rgb:f5f5f5/07ac0a4d-34d2-4fe4-bf4f-b11ce823d012/pro-hyperwarm-hood-m8X0zx.png",
                    productname: "Nike Pro Hyperwarm Hood",
                    productDesc: "Ideal for practicing and playing in cold temperatures, the Nike Pro Hyperwarm Hood features warm, lightweight fabric that covers the face below the neck.",
                    productprice: "$38" 
                },
            ],
        }
    },
    components: {
        Headers,
        Cartitem
    }
}
</script>

<template>
    <header class="WorldNewsHeader">
        <h1>Cart</h1>
    </header>

        <div class="articleGrid">
            <Cartitem v-for="Cartitem in Cartlist" :productItem="Cartitem" :key="Cartitem.productname" />
        </div>
</template>


