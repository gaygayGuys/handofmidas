<template>
    <v-row align="center">
        <v-col cols="12" align-self="center" class="text-center">
            <recommend-table></recommend-table>
        </v-col>
    </v-row>
</template>

<script>
    import RecommendTable from "@/components/RecommendTable";

    export default {
        name: "Recommend",
        components: {
            'recommend-table': RecommendTable
        }
    }
</script>

<style scoped>

</style>