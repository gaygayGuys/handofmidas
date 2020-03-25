<template>
    <v-app id="hand_of_midas">
        <v-app-bar
                app
                clipped-left
                color="amber"
        >
            <v-app-bar-nav-icon @click="drawer = !drawer"/>
            <span class="title ml-3 mr-5">Hand&nbsp;<span class="font-weight-light">of&nbsp;</span>Midas</span>

            <v-spacer></v-spacer>

            <v-btn text>
                <span class="mr-2">share</span>
                <v-icon>mdi-open-in-new</v-icon>
            </v-btn>
        </v-app-bar>

        <v-navigation-drawer
                v-model="drawer"
                app
                clipped
                color="grey lighten-4"
        >
            <v-list
                    dense
                    class="grey lighten-4">
                <template v-for="(item,index) in menus">
                    <v-list-item :key="index" link @click="showComponent=item.component">
                        <v-list-item-action>
                            <v-icon small>{{item.icon}}</v-icon>
                        </v-list-item-action>
                        <v-list-item-content>
                            <v-list-item-title class="grey--text">
                                {{item.title}}
                            </v-list-item-title>
                        </v-list-item-content>
                    </v-list-item>
                    <v-divider :key="index" dark></v-divider>
                </template>
            </v-list>
        </v-navigation-drawer>
        <v-content class="grey lighten-4">
            <v-container>
                <component v-bind:is="showComponent"></component>
            </v-container>
        </v-content>
    </v-app>
</template>

<script>
    import Subject from "@/components/Subject";
    import Recommend from "@/components/Recommend";
    import Calendar from "@/components/Calendar";

    export default {
        name: 'App',
        components: {
            'subject': Subject,
            'recommend': Recommend,
            'calendar': Calendar
        },
        data: () => ({
            drawer: null,
            showComponent: 'subject',
            menus: [
                {
                    'component': 'subject',
                    'icon': 'mdi-text-subject',
                    'title': '题库'
                },
                {
                    'component': 'recommend',
                    'icon': 'mdi-laptop',
                    'title': '内推'
                },
                {
                    'component': 'calendar',
                    'icon': 'mdi-calendar-month-outline',
                    'title': '日程'
                }
            ]
        }),
    };
</script>

<style>
    #hand_of_midas .v-navigation-drawer__border {
        display: none;
    }
</style>
