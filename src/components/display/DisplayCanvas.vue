<template>
   <canvas 
    id="canvass"
    v-show="false" 
   :width="image.width"
   :height="image.height"     > 
        </canvas>
</template>

<script>
    export default {
         computed:{
             image(){
                 return this.$store.getters.getImage
             },
             filters(){
                 return this.$store.getters.getFilters
             }
         },
         watch:{
             filters: {
                 deep:true,
                 handler(){
                    this.loadImageToCanvas();
                 }
              
          },
          image: function(){
               setTimeout(() => {
                   this.loadImageToCanvas();
               }, 1000);
           },
          
         }, 
         methods:{
            loadImageToCanvas(){

              
              const image= document.querySelector('.display-image');
              if(image instanceof HTMLImageElement){
              const canvas=document.getElementById('canvass');
              let ctx = canvas.getContext('2d');
              console.log(ctx);
              ctx.filter=ctx.filterString;
              ctx.drawImage(image,0,0,canvas.width,canvas.height)
              //console.log(image);
              }
           
            },
         },
  
        
    }
</script>

<style scoped>
canvas{
    border: 1px solid black;
}
</style>