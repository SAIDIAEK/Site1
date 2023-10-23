<template>
<section class="bg-gray-200 p-6"> <!-- class="bg-gray-200 p-6" -->
    <header class="flex bg-gray-200 justify-between">  
        <div class="flex items-center">
            <h1 class="font-bold text-lg">My App</h1>
            <p class="text-sm ml-4">Welcome Back, {{ username }}</p>
        </div>

        <Nav />
    </header>
</section>

<section class="p-6">
    <div class="max-w-3xl mx-auto">
        <slot />
    </div>
</section>

</template>
<script>
import Nav from './Nav.vue'
export default{
components: { Nav },
computed:{
        username(){
            return this.$page.props.auth.user.username;
        }
    },
}
</script>
