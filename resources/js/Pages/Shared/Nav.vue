<template>
    <nav >
        <ul class="space-x-6 hidden md:flex">
            <li><NavLink href="/" :active="$page.component === 'Home'">Home</NavLink></li>
            <li><NavLink href="/users" :active="$page.url.startsWith('/users')">Users</NavLink></li>
            <li><NavLink href="/settings" :active="$page.component==='Settings'">Settings</NavLink></li>
            <div v-if="authenticated">
                <li><NavLink href="/logout" method="post" as="button">Log Out</NavLink></li>
            </div>
            <div v-else>
                <li><NavLink href="/login" method="get" as="button">Log In</NavLink></li>
            </div>
        </ul>

        <!-- Mobile Menu Button -->
        <div class="md:hidden">
            
        </div>
    </nav>

</template>

<script>
import NavLink from '@/Shared/NavLink.vue';

export default {
    components: { NavLink },
    computed:{
        authenticated(){
            return this.$page.props.authenticated;
        },
    },
    
    data() {
        return {
        mobileMenuOpen: false,
        };
    },
    methods: {
        toggleMobileMenu() {
            this.mobileMenuOpen = !this.mobileMenuOpen;
        },
    },
}
</script>