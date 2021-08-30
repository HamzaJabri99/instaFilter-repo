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
  
  background: -webkit-linear-gradient(rgb(51, 255, 238), rgb(251, 122, 219));
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}
</style>