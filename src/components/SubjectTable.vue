<template>
    <v-card color="grey lighten-4" outlined style="border: none">
        <v-card-title>
            HTML
            <v-spacer></v-spacer>
            <v-text-field
                    v-model="search"
                    append-icon="mdi-magnify"
                    label="搜索"
                    single-line
                    hide-details
            ></v-text-field>
        </v-card-title>
        <v-data-table class="table-back"
                      :headers="headers"
                      :items="desserts"
                      :search="search"
                      calculate-widths
        >
            <template v-slot:item.content="{item}">
                <a class="a-no-style" href="Https://www.baidu.com" target="_blank">{{item.content}}</a>
            </template>
            <template v-slot:item.contributor="{item}">
                <v-chip href="Https://www.baidu.com"
                        link small outlined
                >{{item.contributorName}}
                </v-chip>
            </template>
        </v-data-table>
    </v-card>
</template>

<script>
    export default {
        name: "SubjectTable",
        data() {
            return {
                search: '',
                headers: [
                    {
                        text: '内容',
                        align: 'start',
                        sortable: false,
                        value: 'content',
                        width: 1000,
                    },
                    {text: '时间', value: 'datetime'},
                    {text: '贡献者', value: 'contributor', sortable: false},
                ],
                desserts: [
                    {
                        content: 'Frozen YogurtFrozen YogurtFrozen YogurtFrozen YogurtFrozen YogurtFrozen YogurtFrozen YogurtFrozen YogurtFrozen YogurtFrozen YogurtFrozen YogurtFrozen YogurtFrozen YogurtFrozen YogurtFrozen YogurtFrozen YogurtFrozen YogurtFrozen YogurtFrozen YogurtFrozen YogurtFrozen Yogurt',
                        datetime: 159,
                        contributorImage: 'https://cdn.vuetifyjs.com/images/john.jpg',
                        contributorName: 'John'
                    },
                    {
                        content: 'Ice cream sandwich',
                        datetime: 237,
                        contributorImage: 'https://cdn.vuetifyjs.com/images/john.jpg',
                        contributorName: 'John'
                    },
                    {
                        content: 'Eclair',
                        datetime: 262,
                        contributorImage: 'https://cdn.vuetifyjs.com/images/john.jpg',
                        contributorName: 'John'
                    },
                    {
                        content: 'Cupcake',
                        datetime: 305,
                        contributorImage: 'https://cdn.vuetifyjs.com/images/john.jpg',
                        contributorName: 'John'
                    },
                    {
                        content: 'Gingerbread',
                        datetime: 356,
                        contributorImage: 'https://cdn.vuetifyjs.com/images/john.jpg',
                        contributorName: 'John'
                    },
                    {
                        content: 'Jelly bean',
                        datetime: 375,
                        contributorImage: 'https://cdn.vuetifyjs.com/images/john.jpg',
                        contributorName: 'John'
                    },
                    {
                        content: 'Lollipop',
                        datetime: 392,
                        contributorImage: 'https://cdn.vuetifyjs.com/images/john.jpg',
                        contributorName: 'John'
                    },
                    {
                        content: 'Honeycomb',
                        datetime: 408,
                        contributorImage: 'https://cdn.vuetifyjs.com/images/john.jpg',
                        contributorName: 'John'
                    },
                    {
                        content: 'Donut',
                        datetime: 452,
                        contributorImage: 'https://cdn.vuetifyjs.com/images/john.jpg',
                        contributorName: 'John'
                    },
                    {
                        content: 'KitKat',
                        datetime: 518,
                        contributorImage: 'https://cdn.vuetifyjs.com/images/john.jpg',
                        contributorName: 'John'
                    },
                ],
            }
        },
    }
</script>

<style scoped>
    .table-back {
        background-color: #f5f5f5 !important;
    }

    .a-no-style {
        text-decoration: none;
        color: #202020;
    }
</style>