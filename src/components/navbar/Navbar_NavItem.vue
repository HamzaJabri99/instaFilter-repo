<template>
    <div class="nav-item flexbox flex-align-center">
    <span class="nav-item-text">{{text}}</span>
    </div>
</template>

<script>
    export default {
        props:['text']
    }
</script>
<style scoped>
.nav-item{
    width: 9rem;

}

</style>