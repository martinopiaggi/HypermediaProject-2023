<!--
    Banner used on top of the single area page
-->
<template>
    <div class="relative w-full">
        <img class="w-full h-[40vh] object-cover md:h-[70vh]" :src="imageUrl" alt="Banner Image"/>
        <div class="absolute font-semibold leading-[4vh] text-4xl left-[5vh] bottom-[3vh] md:mt-[5%] md:text-5xl lg:text-8xl mt-[25%]">
            <h1>WE INVEST IN <br />
            <span v-if="areaCode === 'SPACE_MINING'" class="text-[#F65933]">{{ area.toUpperCase() }}</span>
            <span v-if="areaCode === 'SPACE_TOURISM'" class="text-[#7DD2F4]">{{ area.toUpperCase() }}</span>
            <span v-if="areaCode === 'SATELLITES'" class="text-[#BB86FC]">{{ area.toUpperCase() }}</span></h1>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        imageUrl: String,
        area: String,
        areaCode: String
    }
};
</script>