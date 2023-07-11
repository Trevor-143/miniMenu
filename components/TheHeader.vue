<template>
    <div>
        <nav>
            <div class="logo">
                logo
            </div>
            <div class="side">
                <h1> <nuxt-link to="/">Home</nuxt-link> </h1>
                <h1> <nuxt-link to="/about">About</nuxt-link> </h1>
                <h1> <nuxt-link to="/blog">Blog</nuxt-link> </h1>
                <h1> <nuxt-link to="/contact">Contact</nuxt-link> </h1>
            </div>
            <h3 class="toggler" @click="smallMenuToggle" >Menu</h3>
            <div class="smenu" v-if="smallMenu" >
                <h1> <nuxt-link to="/">Home</nuxt-link> </h1>
                <h1> <nuxt-link to="/about">About</nuxt-link> </h1>
                <h1> <nuxt-link to="/blog">Blog</nuxt-link> </h1>
                <h1> <nuxt-link to="/contact">Contact</nuxt-link> </h1>
            </div>
        </nav>
    </div>
</template>

<script setup>
const smallMenu = ref(false)
const smallMenuToggle = () => {
    smallMenu.value = !smallMenu.value
} 
</script>

<style>
nav{
    display: flex;
    background-color: orange;
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    align-items: center;
    display: flex;
    justify-content: space-between;
}
.side {
    display: flex;
}
h1 {
    font-size: 1rem;
    margin: 1rem;
}
.toggler {
    display: none;
}

@media (max-width:600px) {
    .toggler {
        display: block;
    }
    .side {
        display: none;
    }
    .smenu {
        position: fixed;
        top: 0;
        left: 0;
        background-color: black;
        color: white;
        display: flex;
        flex-direction: column;
    }
}

</style>