    <template>
        <div class="w-full min-h-screen bg-[url('@/assets/images/blackbg.png')] relative overflow-hidden">
            <!-- Animated background elements -->
            <div class="absolute inset-0 overflow-hidden opacity-20">
                <div v-for="i in 20" :key="i" class="absolute rounded-full bg-blue-400" :class="`circle-${i}`"></div>
            </div>

            <div class="h-[100vh] max-h-screen">
                <v-row class="h-full items-center">
                    <!-- Text content -->
                    <v-col cols="12" md="6" class="py-8 md:py-16">
                        <div class="text-blue-300 font-mono text-lg mb-2">Hello World! 👋</div>

                        <h1 class="text-4xl md:text-6xl font-bold mb-4">
                            I'm <span
                                class="text-transparent bg-clip-text bg-gradient-to-r from-blue-400 to-cyan-300">Gurumurugan
                                L</span>
                        </h1>

                        <div class="text-2xl md:text-3xl font-semibold mb-6 text-blue-200 h-12">
                            <v-slide-y-reverse-transition group>
                                <span v-for="(role, i) in roles" :key="role" v-show="activeRole === i" class="absolute">
                                    {{ role }}
                                </span>
                            </v-slide-y-reverse-transition>
                        </div>

                        <p class="text-gray-300 text-lg mb-8 max-w-lg">
                            Full Stack Developer specializing in Vue.js, SQL and Go. I build performant, scalable web
                            applications with clean code and intuitive UX.
                        </p>

                        <div class="flex flex-wrap gap-4">
                            <v-btn size="x-large" color="blue" class="font-bold px-8" rounded="lg" variant="flat">
                                View Projects
                                <v-icon end icon="mdi-arrow-right"></v-icon>
                            </v-btn>

                            <v-btn size="x-large" class="font-bold px-8" rounded="lg" variant="outlined" color="white">
                                Contact Me
                            </v-btn>
                        </div>

                        <div class="mt-8 flex gap-4">
                            <v-btn v-for="(social, i) in socialLinks" :key="i" :href="social.link" target="_blank"
                                :icon="social.icon" variant="text" size="large" :color="social.color"></v-btn>
                        </div>
                    </v-col>

                    <!-- Profile image - shown only on medium+ screens -->
                    <v-col cols="12" md="6" class="hidden md:flex justify-center items-center">
                        <div class="relative group">
                            <div
                                class="absolute -inset-2 bg-blue-500 rounded-full opacity-0 group-hover:opacity-20 blur-md transition-opacity duration-300">
                            </div>
                            <v-avatar size="600"
                                class="border-4 border-blue-400/10 group-hover:border-blue-400/30 transition-all duration-300 relative z-10">
                                <v-img src="@/assets/images/guru01.jpg" alt="Profile Image"
                                    class="group-hover:scale-105 transition-transform duration-300" />
                            </v-avatar>
                            <!-- <div
                                class="absolute -bottom-6 left-1/2 transform -translate-x-1/2 bg-blue-500 text-white px-4 py-2 rounded-full shadow-lg">
                                <span class="font-bold">Open for opportunities</span>
                            </div> -->
                        </div>
                    </v-col>
                </v-row>
            </div>

            <!-- Scroll indicator -->
            <div class="absolute bottom-8 left-1/2 transform -translate-x-1/2">
                <v-icon icon="mdi-chevron-double-down" size="large" color="white" class="animate-bounce"></v-icon>
            </div>
        </div>
    </template>

    <script setup>
    import { ref, onMounted } from 'vue'

    const roles = [
        'Full Stack Developer',
        'Vue.js Specialist',
        'Go Enthusiast',
        'Problem Solver'
    ]
    const activeRole = ref(0)

    const socialLinks = [
        { icon: 'mdi-github', color: 'grey-lighten-2', link: 'https://github.com' },
        { icon: 'mdi-linkedin', color: 'blue-lighten-2', link: 'https://linkedin.com' },
        // { icon: 'mdi-twitter', color: 'blue-lighten-1', link: 'https://twitter.com' },
        { icon: 'mdi-email', color: 'yellow-lighten-2', link: 'mailto:guru292001@gmail.com' }
    ]

    // Role rotation animation
    onMounted(() => {
        setInterval(() => {
            activeRole.value = (activeRole.value + 1) % roles.length
        }, 2000)
    })
    </script>

    <style scoped>
    /* Background circle animations */
    .circle-1 {
        width: 100px;
        height: 100px;
        top: 10%;
        left: 13%;
        animation: float 10s ease-in-out infinite;
    }

    .circle-2 {
        width: 300px;
        height: 300px;
        top: 50%;
        left: 80%;
        animation: float 20s ease-in-out infinite reverse;
    }

    /* Add more circle styles as needed */

    @keyframes float {

        0%,
        100% {
            transform: translateY(0) translateX(0);
        }

        50% {
            transform: translateY(-20px) translateX(10px);
        }
    }
    </style>