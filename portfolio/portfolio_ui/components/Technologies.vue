<template>
    <v-row class="justify-center pa-0 ma-0" align="center">
        <v-col v-for="(item, idx) in topics" :key="idx" cols="11" sm="5" md="4" lg="3" class="d-flex justify-center">
            <div
                class="relative w-full max-w-sm h-[350px] bg-white/10  border border-white/20 rounded-2xl shadow-xl transition-transform transform hover:scale-105 hover:shadow-2xl p-6 flex flex-col justify-center items-center group">
                <!-- Floating Image -->
                <img :src="item.image" alt="icon"
                    class="w-24 h-24 object-contain mb-4 transition-transform duration-500 group-hover:-translate-y-2" />

                <!-- Title -->
                <h3 class="text-xl font-bold text-black mb-2 text-center">
                    {{ item.title }}
                </h3>

                <!-- Description -->
                <p class="text-Black/80 text-sm text-center px-2">
                    {{ item.description }}
                </p>

                <!-- Gradient border effect -->
                <div
                    class="absolute -inset-[2px] z-[-1] rounded-2xl bg-gradient-to-b from-stone-50 via-sky-200 to-blue-300 opacity-100 group-hover:opacity-100 transition-opacity duration-500">
                </div>
            </div>
        </v-col>
    </v-row>
</template>

<script setup>
const topics = [
    {
        title: "UI/UX",
        description: "Crafting beautiful and intuitive interfaces.",
        image: "https://img.icons8.com/color/96/design.png"
    },
    {
        title: "Programming",
        description: "Writing efficient and scalable code.",
        image: "https://img.icons8.com/color/96/source-code.png"
    },
    {
        title: "Database Management",
        description: "Handling data with precision and security.",
        image: "https://img.icons8.com/color/96/database.png"
    },
    //   {
    //     title: "Computer Basics",
    //     description: "Fundamentals of computing and systems.",
    //     image: "https://img.icons8.com/color/96/computer.png"
    //   },
    //   {
    //     title: "Data Analysis",
    //     description: "Turning data into insights.",
    //     image: "https://img.icons8.com/color/96/combo-chart--v1.png"
    //   }
]
</script>

<style scoped>
/* Optional: smooth transition for group hover */
.group:hover img {
    transform: translateY(-10px);
}

</style>
