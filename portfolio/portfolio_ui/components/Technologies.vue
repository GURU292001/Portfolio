<template>
<div class="text-4xl font-sans text-center mb-3 font-bold bg-gradient-to-t from-gray-600 to-gray-100 bg-clip-text text-transparent">
  Technologies
</div>
    <div>
        <v-row class="justify-center pa-0 ma-0" align="center">
            <v-col v-for="(item, idx) in topics" :key="idx" cols="12" lg="3" class="">

                <v-card class="px- mx-2 text-center rounded-lg " height="350">
                    <div
                        class="bg-gradient-to-b from-stone-50 via-sky-200 to-blue-300 h-full  p-6 flex flex-col justify-center items-center group ">
                        <v-card-title>{{ item.title }}</v-card-title>
                        <v-card-text class="d-flex flex-column justify-center">
                            <span class="d-flex justify-center">
                                <v-img :src="item.image" width="50" height="50"></v-img>
                            </span>
                            <span>{{ item.description }}</span>
                        </v-card-text>
                    </div>

                </v-card>
                <v-card class="mt-2 mx-2 rounded-lg">
                    <div class="h-full bg-gradient-to-t from-gray-300 to-gray-100">
                        <v-card-text class="d-flex flex-row flex-wrap  ">
                          
                            <v-img :src="item.icons[0]" width="50" height="50"></v-img>
                        </v-card-text>
                    </div>
                </v-card>
            </v-col>
        </v-row>
    </div>

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
