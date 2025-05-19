<template>
     <span  class="  h-[500vh] bg-[url('@/assets/images/blackbg.png')] bg-repeat-y  ">
        <About />
        <Technologies />
        <Project/>
        <Timeline/>

    </span>
</template>
<script setup>
import About from '~/components/About.vue';
import Technologies from '~/components/Technologies.vue';
import Project from '~/components/Project.vue';
import Timeline from '~/components/Timeline.vue';
</script>

