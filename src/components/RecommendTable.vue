<template>
    <v-card color="grey lighten-4" outlined style="border: none">
        <v-card-title>
            内推
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
            <template v-slot:item.company="{item}">
                <div>
                    <p class="subtitle-2 no-mb">{{item.companyName}}</p>
                    <p class="caption no-mb">
                        <a class="a-no-style" href="Https://www.baidu.com" target="_blank">{{item.companyWebSite}}</a>
                    </p>
                </div>
            </template>
            <template v-slot:item.contributor="{item}">
                <v-chip href="Https://www.baidu.com"
                        link small outlined
                >{{item.contributorName}}
                </v-chip>
            </template>
            <template v-slot:item.operation>
                <a class="a-no-style" href="Https://www.baidu.com" target="_blank">查看</a>
            </template>
        </v-data-table>
    </v-card>
</template>

<script>
    export default {
        name: "RecommendTable",
        data() {
            return {
                search: '',
                headers: [
                    {
                        text: '公司',
                        align: 'start',
                        sortable: false,
                        value: 'company',
                        width: 1000,
                    },
                    {text: '时间', value: 'datetime'},
                    {text: '贡献者', value: 'contributor', sortable: false},
                    {text: '操作', value: 'operation', sortable: false},
                ],
                desserts: [
                    {
                        companyName: 'Frozen Yogurt',
                        companyWebSite: 'Https://www.baidu.com',
                        datetime: 159,
                        contributorImage: 'https://cdn.vuetifyjs.com/images/john.jpg',
                        contributorName: 'John'
                    },
                    {
                        companyName: 'Ice cream sandwich',
                        companyWebSite: 'Https://www.baidu.com',
                        datetime: 237,
                        contributorImage: 'https://cdn.vuetifyjs.com/images/john.jpg',
                        contributorName: 'John'
                    },
                    {
                        companyName: 'Eclair',
                        companyWebSite: 'Https://www.baidu.com',
                        datetime: 262,
                        contributorImage: 'https://cdn.vuetifyjs.com/images/john.jpg',
                        contributorName: 'John'
                    },
                    {
                        companyName: 'Cupcake',
                        companyWebSite: 'Https://www.baidu.com',
                        datetime: 305,
                        contributorImage: 'https://cdn.vuetifyjs.com/images/john.jpg',
                        contributorName: 'John'
                    },
                    {
                        companyName: 'Gingerbread',
                        companyWebSite: 'Https://www.baidu.com',
                        datetime: 356,
                        contributorImage: 'https://cdn.vuetifyjs.com/images/john.jpg',
                        contributorName: 'John'
                    },
                    {
                        companyName: 'Jelly bean',
                        companyWebSite: 'Https://www.baidu.com',
                        datetime: 375,
                        contributorImage: 'https://cdn.vuetifyjs.com/images/john.jpg',
                        contributorName: 'John'
                    },
                    {
                        companyName: 'Lollipop',
                        companyWebSite: 'Https://www.baidu.com',
                        datetime: 392,
                        contributorImage: 'https://cdn.vuetifyjs.com/images/john.jpg',
                        contributorName: 'John'
                    },
                    {
                        companyName: 'Honeycomb',
                        companyWebSite: 'Https://www.baidu.com',
                        datetime: 408,
                        contributorImage: 'https://cdn.vuetifyjs.com/images/john.jpg',
                        contributorName: 'John'
                    },
                    {
                        companyName: 'Donut',
                        companyWebSite: 'Https://www.baidu.com',
                        datetime: 452,
                        contributorImage: 'https://cdn.vuetifyjs.com/images/john.jpg',
                        contributorName: 'John'
                    },
                    {
                        companyName: 'KitKat',
                        companyWebSite: 'Https://www.baidu.com',
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

    .no-mb {
        margin-bottom: 0;
    }
</style>