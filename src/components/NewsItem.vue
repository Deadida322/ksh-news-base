<template>
    <v-card>
        <v-img height="200px" :src="news.img"></v-img>
        <v-card-subtitle class="mb-0 pb-0">
            <div class="d-flex align-center justify-space-between">
                <div class="text">
                    {{ news.date }}
                </div>
                <div class="tags">
                    <v-chip v-for="tag in news.tags.slice(0, 3)" class="ma-1" :color="getRandomColor()" outlined>
                        {{ tag }}
                    </v-chip>
                </div>
            </div>

        </v-card-subtitle>
        <v-card-title>{{ news.title }}</v-card-title>
        <v-card-text>
            <div>
                {{ news.description.slice(0, 300) }}...
            </div>
        </v-card-text>
        <v-card-actions>
            <v-spacer></v-spacer>
            <v-btn color="orange" text>
                Подробнее
            </v-btn>
        </v-card-actions>
    </v-card>
</template>

<script>
export default {
    data() {
        return {

        }
    },
    props: {
        news: {
            type: Object,
            required: true
        }
    },
    methods: {
        getRandomColor() {
            const colors = ['success', "error", "warning", 'deep-purple accent-4', 'indigo darken-3', 'primary']

            return colors[Math.round(Math.random() * colors.length)]
        }
    }
}
</script>