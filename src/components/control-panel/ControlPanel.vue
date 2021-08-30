<template>
    <div class="control-panel flex-1 flexbox flexdir-col">
     <ImageLoader/>
     <FilterPanel/>
   <SaveImagePanel/>
    </div>
</template>

<script>
import ImageLoader from './ImageLoader'
import FilterPanel from './filter-panel/FilterPanel'
import SaveImagePanel from './Save-Image/SaveImagePanel'
    export default {
        components:{
            ImageLoader,
            FilterPanel,
            SaveImagePanel
        }
    }
</script>

<style scoped>
.control-panel{
    border-right: 3px solid black;
    background: #c77dff;
    
}
@media screen and (max-width:600px){
    .control-panel{
    min-width: 50%;

    }
}
</style>