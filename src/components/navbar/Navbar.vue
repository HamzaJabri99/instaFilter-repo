<template>
    <nav class="navbar-outer flexbox">
    <navbar-brand title="InstaFilter" class="brand"></navbar-brand>
    
    <navbar-item text="Home"></navbar-item>
    <navbar-item text="About"></navbar-item>
    <navbar-item text="Contact"></navbar-item>
    

    </nav>
</template>

<script>
import Navbar_Brand from './Navbar_Brand'
import Navbar_NavItem from './Navbar_NavItem'
    export default {
        components:{
         'navbar-brand':Navbar_Brand,
         'navbar-item':Navbar_NavItem
        }
    }
</script>

<style scoped>
.navbar-outer{
    height: 60px;
    background-color: var(--coldarkblue);
}
@media screen and (max-width: 600px){
.navbar-outer{
    width: 100%;
    font-size: 0.84rem;
    padding: 0.5rem;
}
.brand{
    margin-right: 0.5rem;
    padding: 0;
}
}
</style>