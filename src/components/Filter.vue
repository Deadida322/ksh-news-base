<template>
    <v-card>
        <v-card-title>Фильтр поиска</v-card-title>
        <v-card-text>
            <div class="d-flex">
                <v-text-field v-model="filter.dateFrom" type="date" outlined label="Дата от"
                    hint="Укажите дату от"></v-text-field>
                <v-text-field v-model="filter.dateTo" type="date" outlined label="Дата до"
                    hint="Укажите дату до"></v-text-field>
            </div>
            <v-text-field v-model="filter.tag" outlined label="Теги" hint="Укажите теги"></v-text-field>
        </v-card-text>
        <v-card-actions>
            <v-spacer></v-spacer>
            <v-btn @click="submit" color="success">
                Применить
            </v-btn>
        </v-card-actions>
    </v-card>
</template>

<script>
export default {
    data: () => ({
        filter: {}
    }),
    methods: {
        submit() {
            this.$emit('apply-filter', this.filter)
        }
    }
}
</script>

