<template>
    <div class="w-full h-[100vh] bg-[url('@/assets/images/blackbg.png')] d-flex justify-center">
        <v-row class="text-white d-flex justify-space-around">
            <!-- I'M Section -->
            <v-col cols="12" md="4" class="d-flex justify-center align-center">
                <span class="text-6xl font-bold ">
                    Hello , I'M 
                </span> &nbsp; &nbsp;
                <span class="text-6xl font-bold text-sky-500 " >Guru</span>
            </v-col>

            <!-- Image Section -->
            <v-col cols="12" md="4" class="d-flex justify-center align-center mb-4 mb-md-0">
                <v-avatar size="500">
                    <v-img src="@/assets/images/blackbg.png" alt="Profile Image" />
                </v-avatar>
            </v-col>

            <!-- Content Section
             <v-col cols="12" md="4" class="d-flex flex-column justify-center align-center">
                <div class="text-xl font-semibold mb-2 text-primary">
                    Full Stack Developer
                </div>
                <div class="text-sm text-gray-300">
                    Passionate about building modern web applications using Vue & Go.
                </div>
            </v-col> -->
         
        </v-row>
    </div>
</template>
