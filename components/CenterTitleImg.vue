<!--
    Centered title with image background or 3D planet visualization
-->
<template>
    <div class='overflow-hidden bigTitle ml-auto mr-auto bg-top md:bg-center-down md:h-full bg-contain md:bg-auto' :style="bgImage + ' ' + customWidth + ' ' + customPos">
        <div v-if="planet" class="z-[0] xl:mt-[10vh] lg:mt-[6vh] md:mt-[4vh] absolute"><Planet3d :texture="planet" ></Planet3d></div>
        <div class="flex flex-col md:min-h-[50vh] h-full">
            <div class="testo z-[1] w-[95%] flex flex-col h-full ml-auto mr-auto"> 
                <div class="md:max-w-[75vw] mr-auto ml-auto text-[2.5rem] leading-tight mt-auto mb-auto md:text-8xl lg:text-9xl text-center md:h-auto inline-block align-center">
                    
                <div v-if="subtitle" class="hidden md:visible mt-20">
                
                </div> 
                    <h1>{{ title }} </h1>  
                <div v-if="subtitle" class="text-2xl uppercase md:text-[3.2rem] lg:text-[3.35rem] md:leading-tight lg:leading-tight  text-center mt-4 md:mt-8 font-ABClight">
                    <h2>{{ subtitle }}</h2>
                </div> 
                </div>            
                <div v-if="description" class="text-lg md:text-4xl lg:text-5xl  text-justify !leading-snug uppercase inline-block align-baseline">
                    <h2>{{ description }}</h2>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        title: String,
        subtitle: String,
        description: String,
        img: String,
        widthImage: String,
        posImage: String,
        planet: String,
    },
    computed: {
        bgImage () {
            if(this.planet) return `background-image: url();`;
            return `background-image: url("${this.img}");`;
        },
        customWidth () {
            return `background-size: ${this.widthImage?this.widthImage:'75%'};`;
        },
        customPos () {
            return `background-position: ${this.posImage?this.posImage:'center'};`;
        }
}
}
</script>


<style scoped>

.bigTitle {
    background-repeat: no-repeat;
}

.testo{    
    font-family: bold;
}

</style>