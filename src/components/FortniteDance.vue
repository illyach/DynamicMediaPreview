<template>
    <div class="my-comp">
      
            <!-- start image -->
            <div  class="div-img" v-show="stateHover"   @mouseover="handleHover" @mouseout="handleHover">
                <img  class="v-img" src="../assets/tf2photo.png" alt="tf2photo">
            </div>
    
            <!-- video content  -->
            <div  class="div-vid" v-show="!stateHover" @mouseover="handleHover" @mouseout="handleHover">
                <video ref="myVideo" class="v-vid" autoplay muted   loop playsinline>
                    <source src="../assets/tf2video.mp4" type="video/mp4" />
                    Sorry, your browser doesn't support videos.
                </video>
            </div>
    
    </div>
</template>

<script setup>
import { ref } from 'vue';
const stateHover = ref(true) 

const handleHover =  () => {
    if(stateHover.value){
        console.log('mouse over')
    }else{
        console.log('mouse out')
    }
    stateHover.value = !stateHover.value
}

</script>

<style>
body , div , video {
    margin: 0;
    padding:0
}

* {
 box-sizing: border-box;
}

.my-comp{
    display: flex;
    flex-direction: column;
    align-items:center;
    margin-top: 60px;
}

.my-comp > div{
    margin:10px;
}


.v-img{
    min-width: 360px;
    height: 255px;
    border-radius: 10px; 
}

.div-img{
    width: 420px;
    height: 255px;
    overflow: hidden;
    border-radius: 10px;
}

.div-vid{
    width: 420px;
    height: 255px;
    overflow: hidden;
    border-radius: 10px; 

}

.v-vid{
    min-width: 360px;
    height: 260px;
}

</style>


