<template>
    <div class="control-panel flex-1 flexbox flexdir-col">
     <ImageLoader/>
     <FilterPanel/>
     <ImageType></ImageType>
    </div>
</template>

<script>
import ImageLoader from './ImageLoader'
import FilterPanel from './filter-panel/FilterPanel'
import ImageType from '../image_Export/ImageType.vue'
    export default {
        components:{
            ImageLoader,
            FilterPanel,
            ImageType
        }
    }
</script>

<style scoped>
.control-panel{
    border-right: 3px solid black;
    background: var(--collightblue);
}
@media screen and (max-width:600px){
    .control-panel{
    max-width: 50%;
    
    }
}
</style>