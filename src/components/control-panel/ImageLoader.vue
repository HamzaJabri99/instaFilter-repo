<template>
    <div class="image-loader flex-1">
       <label for="image-loader">Load Image</label>
       <input 
        class="image-loader-input" 
        type="text" 
        id="image-loader"
        @input="setImageSource_STORE($event.target.value)">
    </div>
</template>

<script>
 import eventBus from '../../eventBus'
 import { mapActions } from 'vuex'
    export default {

        methods:{
            ...mapActions(['setImageSource_STORE'])
        }
 
    }
</script>

<style scoped>
.image-loader{
    padding: .5rem 1rem;
    color: #240046;
    font-weight: bolder;
    
}
label{
    font-size: 170%;
    margin-bottom: 10rem;
}
.image-loader-input{
    font-size: 1.1rem;
    padding: .1rem .25rem;
    outline: none;
    margin: 1rem 0rem 1.6rem 0rem;
    border: 2px solid #212121;
    border-radius: 5px;
    
}
@media screen and (max-width:600px){
 
    .image-loader-input{
        width: 100%;
    }
}
</style>

