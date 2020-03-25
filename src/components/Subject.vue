<template>
    <v-row>
        <v-col>
            <v-row align="center">
                <template v-for="(item,index) in category">
                    <v-col cols="2" align-self="center" class="text-center" :key="index">
                        <v-btn text>
                            <v-icon small>{{item.icon}}</v-icon>
                            <span>{{item.title}}</span>
                        </v-btn>
                    </v-col>
                </template>
            </v-row>
            <v-row align="center">
                <v-col cols="12" align-self="center" class="text-center">
                    <subject-table></subject-table>
                </v-col>
            </v-row>
        </v-col>
    </v-row>
</template>

<script>
    import SubjectTable from "@/components/SubjectTable";

    export default {
        name: "Subject",
        components: {
            'subjectTable': SubjectTable
        },
        data: () => ({
            category: [
                {
                    'icon': 'mdi-language-html5',
                    'title': 'Html'
                },
                {
                    'icon': 'mdi-language-javascript',
                    'title': 'JavaScript'
                },
                {
                    'icon': 'mdi-ip-network',
                    'title': 'Http'
                },
                {
                    'icon': 'mdi-react',
                    'title': 'React'
                },
                {
                    'icon': 'mdi-vuejs',
                    'title': 'Vue'
                },
                {
                    'icon': 'mdi-language-css3',
                    'title': 'Css'
                },
                {
                    'icon': 'mdi-web',
                    'title': 'Web'
                },
                {
                    'icon': 'mdi-language-java',
                    'title': 'Java'
                }
            ]
        })
    }
</script>

<style scoped>

</style>