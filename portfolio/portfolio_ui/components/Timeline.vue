<template>
  <v-row class="mx-auto align-center justify-center">
        <v-col cols="12" lg="6">
             <v-timeline align="start">
        <v-timeline-item v-for="(item, i) in items" :key="i" :dot-color="item.color" :line-thickness="10" :icon="item.icon" fill-dot>
            <v-card>
                <v-card-title :class="['text-h6', `bg-${item.color}`]">
                    {{ item.name }}
                </v-card-title>
                <v-card-text class="bg-white text--primary pt-3">
                   <span>  {{ item.description }}</span>
                    <!-- <v-btn :color="item.color" variant="outlined">
                        Button
                    </v-btn> -->
                </v-card-text>
            </v-card>
        </v-timeline-item>
    </v-timeline>
        </v-col>
  </v-row>
    
</template>
<script>
export default {
    data: () => ({
        items: [
            {
                name: 'grey Ipsum Dolor',
                image:``,
                description: 'Lorem ipsum dolor sit amet, no nam oblique veritus. Commune scaevola imperdiet nec ut, sed euismod convenire principes at. Est et nobis iisque percipit, an vim zril disputando voluptatibus, vix an salutandi sententiae.',
                color: 'red-lighten-2',
                icon: 'mdi-star',
            },
            {
                name: 'Lorem Ipsum Dolor',
                image:``,
                description: 'Lorem ipsum dolor sit amet, no nam oblique veritus. Commune scaevola imperdiet nec ut, sed euismod convenire principes at. Est et nobis iisque percipit, an vim zril disputando voluptatibus, vix an salutandi sententiae.',
                color: 'blue-lighten-2',
                icon: 'mdi-book-variant',
            },
           
        ],
    }),
}
</script>