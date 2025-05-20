<template>
     <div  class=" h-[500vh]  bg-[url('/images/blackbg.png')]  bg-repeat-y  ">
        <About />
        <Technologies />
        <Project/>
        <Timeline/>

     </div>
</template>
<script setup>
import About from '~/components/About.vue';
import Technologies from '~/components/Technologies.vue';
import Project from '~/components/Project.vue';
import Timeline from '~/components/Timeline.vue';
</script>

