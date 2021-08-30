<template>
    <div class="navbar-brand flex-1 flexbox flex-align-center">
        <h2 class="navbar-brand-text">
            {{ title }}
        </h2>
    </div>
</template>

<script>
    export default {
        props:['title']
        }
    
</script>

<style scoped>
.navbar-brand{
    padding-left: 1.5rem;
    
}
h2{
  font-weight: bold;
  background: -webkit-linear-gradient(#c77dff,#e0aaff);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}
@media screen and (max-width:600px) {
       .navbar-brand{
       font-weight: 100; 
    }
}
</style>