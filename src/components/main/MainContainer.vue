<template>
    <div class="main-container flex-1 flexbox">
        <ControlPanel/>
        <DisplayContainer/>
    </div>
    
</template>

<script>
import ControlPanel from '../control-panel/ControlPanel.vue'
import DisplayContainer from '../display/DisplayContainer.vue'
    export default {
        components:{
            ControlPanel,
            DisplayContainer
        }
    }
</script>

<style scoped>
.main-container{
    background-color: rgb(241, 241, 241);
}
</style>