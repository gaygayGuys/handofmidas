<template>
    <v-row class="fill-height">
        <v-col>
            <v-sheet>
                <v-toolbar flat color="grey lighten-4">
                    <v-btn outlined class="mr-4" color="grey darken-2" @click="setToday">
                        今日
                    </v-btn>
                    <v-btn fab text small color="grey darken-2" @click="prev">
                        <v-icon small>mdi-chevron-left</v-icon>
                    </v-btn>
                    <v-btn fab text small color="grey darken-2" @click="next">
                        <v-icon small>mdi-chevron-right</v-icon>
                    </v-btn>
                    <v-toolbar-title>{{ title }}</v-toolbar-title>
                    <v-spacer></v-spacer>
                    <v-menu bottom right>
                        <template v-slot:activator="{ on }">
                            <v-btn
                                    outlined
                                    color="grey darken-2"
                                    v-on="on"
                            >
                                <span>{{ typeToLabel[type] }}</span>
                                <v-icon right>mdi-menu-down</v-icon>
                            </v-btn>
                        </template>
                        <v-list>
                            <v-list-item @click="type = 'day'">
                                <v-list-item-title>日</v-list-item-title>
                            </v-list-item>
                            <v-list-item @click="type = 'week'">
                                <v-list-item-title>周</v-list-item-title>
                            </v-list-item>
                            <v-list-item @click="type = 'month'">
                                <v-list-item-title>月</v-list-item-title>
                            </v-list-item>
                        </v-list>
                    </v-menu>
                </v-toolbar>
            </v-sheet>
            <v-sheet>
                <v-calendar
                        ref="calendar"
                        v-model="focus"
                        color="primary"
                        :now="today"
                        :type="type"
                        @click:more="viewDay"
                        @click:date="viewDay"
                        @change="updateRange"
                        locale="zhHans"
                ></v-calendar>
            </v-sheet>
        </v-col>
    </v-row>
</template>

<script>
    export default {
        name: "Calendar",
        data: () => ({
            focus: '',
            type: 'month',
            typeToLabel: {
                month: '月',
                week: '周',
                day: '日'
            },
            start: null,
            end: null,
        }),
        computed: {
            title() {
                const {start, end} = this;
                if (!start || !end) {
                    return ''
                }
                const startMonth = this.monthFormatter(start);
                const endMonth = this.monthFormatter(end);
                const suffixMonth = startMonth === endMonth ? '' : endMonth;
                const startYear = start.year + '年';
                const endYear = end.year + '年';
                const suffixYear = startYear === endYear ? '' : endYear;
                const startDay = start.day + '日';
                const endDay = end.day + '日';
                switch (this.type) {
                    case 'month':
                        return `${startMonth} ${startYear}`;
                    case 'week':
                        return `${startMonth} ${startDay} ${startYear} - ${suffixMonth} ${endDay} ${suffixYear}`;
                    case 'day':
                        return `${startMonth} ${startDay} ${startYear}`;
                }
                return ''
            },
            monthFormatter() {
                return this.$refs.calendar.getFormatter({
                    timeZone: 'UTC', month: 'long',
                });
            },
        },
        mounted() {
            this.$refs.calendar.checkChange();
        },
        methods: {
            viewDay({date}) {
                this.focus = date;
                this.type = 'day';
            },
            setToday() {
                this.focus = this.today;
            },
            prev() {
                this.$refs.calendar.prev();
            },
            next() {
                this.$refs.calendar.next();
            },
            updateRange({start, end}) {
                this.start = start;
                this.end = end;
            },
        },
    }
</script>

<style scoped>

</style>