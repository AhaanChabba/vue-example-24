<script>
import Header from '../Header.vue'
import Footer from '../Footer.vue'
import Cart from '../pages/Cart.vue'
export default {
    data() {
        return {
            description: "Welcome to Fotmob",
            copy: "This is copy. It's a string. Paragraph paragraph paragraph.",
        }
    }, 
    components: {
        Header,
        Footer,
        Cart,

      
    }
}
</script>

<template>
   
    <div class="backgroundWithImage">
        <div class="description">
            <p>home</p>
            <h1>{{ description }}</h1>
        </div>
    </div>
    <div>
        {{ copy }}
    </div>
  
</template>

<style scoped>
.backgroundWithImage {
    height: calc(-200px + 150vh);
    background-size: 150%;  
    background-repeat: no-repeat;
    background-image: url(https://latest.fotmob.com/wp-content/uploads/2024/03/Covers_EPL-Review-0403-1.png);
}

.description {
    color: var(--color-heading);
    display: flex;
    flex-direction: column;
    -webkit-box-pack: center;
    justify-content: center;
    max-width: min(80%, 940px);
    height: calc(-50px + 100vh);
    margin: 0 auto; /* auto-center */ 
}
.description * {
    margin: 0;
}
</style>