<template>

    <div
        class="text-4xl font-sans text-center ma-3 font-bold bg-gradient-to-t from-gray-600 to-gray-100 bg-clip-text text-transparent">
        Projects
    </div>
    <v-row class="mx-auto align-center justify-center">
        <v-col cols="12" lg="6">
            <v-card  v-for="(item, idx) in topics" :key="idx" class="mx-auto my-2 rounded-lg ">
                <div class="bg-gradient-to-r from-red-800  to-sky-800 h-fill w-fill">
                    <v-card-text>
                        <v-row>
                            <v-col cols="12" lg="6" class="d-flex justify-center">
                                <v-card width="300" height="250" class="rounded-lg">
                                    <v-card-title>
                                        {{ item.title }}
                                    </v-card-title>
                                    <v-card-text>
                                        <v-img :src="item.image" cover></v-img>
                                    </v-card-text>
                                </v-card>

                            </v-col>
                            <v-col cols="12" lg="6" class="d-flex justify-start">
                                <span class="text-white">Project Name</span> <br>
                                <span class="text-white">Project Description</span>
                            </v-col>
                        </v-row>
                    </v-card-text>
                </div>
            </v-card>
        </v-col>
    </v-row>
</template>
<script setup>
const topics = [
    {
        title: "UI/UX Design",
        description: "Crafting beautiful and intuitive interfaces.",
        image: "https://img.icons8.com/color/96/design.png",
        icons: [
            "/images/Tech Stack Logos.png",
            "https://img.icons8.com/color/48/figma.png",
            "https://img.icons8.com/color/48/figma.png",
            "https://img.icons8.com/color/48/figma.png",
            "https://img.icons8.com/color/48/figma.png",
        ]
    },
    {
        title: "Programming",
        description: "Writing efficient and scalable code.",
        image: "https://img.icons8.com/color/96/source-code.png",
        icons: [
            "https://img.icons8.com/color/48/golang.png",
            "https://img.icons8.com/color/48/java-coffee-cup-logo--v1.png"
        ]
    },
    {
        title: "Database Management",
        description: "Handling data with precision and security.",
        image: "https://img.icons8.com/color/96/database.png",
        icons: [
            "https://img.icons8.com/color/48/mysql-logo.png"
        ]
    }
];
</script>