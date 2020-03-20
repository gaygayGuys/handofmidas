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
                <v-list-item link>
                    <v-list-item-action>
                        <v-icon small>mdi-text-subject</v-icon>
                    </v-list-item-action>
                    <v-list-item-content>
                        <v-list-item-title class="grey--text">
                            面试题
                        </v-list-item-title>
                    </v-list-item-content>
                </v-list-item>
                <v-divider dark></v-divider>
                <v-list-item link>
                    <v-list-item-action>
                        <v-icon small>mdi-laptop</v-icon>
                    </v-list-item-action>
                    <v-list-item-content>
                        <v-list-item-title class="grey--text">
                            内推
                        </v-list-item-title>
                    </v-list-item-content>
                </v-list-item>
                <v-divider dark></v-divider>
                <v-list-item link>
                    <v-list-item-action>
                        <v-icon small>mdi-calendar-month-outline</v-icon>
                    </v-list-item-action>
                    <v-list-item-content>
                        <v-list-item-title class="grey--text">
                            日历
                        </v-list-item-title>
                    </v-list-item-content>
                </v-list-item>
                <v-divider dark></v-divider>
            </v-list>
        </v-navigation-drawer>
        <v-content class="grey lighten-4">
            <v-container>
                <v-row align="center">
                    <v-col cols="2" align-self="center" class="text-center">
                        <v-btn text>
                            <v-icon small>mdi-language-html5</v-icon>
                            <span>Html</span>
                        </v-btn>
                    </v-col>
                    <v-col cols="2" align-self="center" class="text-center">
                        <v-btn text>
                            <v-icon small>mdi-language-javascript</v-icon>
                            <span>JavaScript</span>
                        </v-btn>
                    </v-col>
                    <v-col cols="2" align-self="center" class="text-center">
                        <v-btn text>
                            <v-icon small>mdi-ip-network</v-icon>
                            <span>Http</span>
                        </v-btn>
                    </v-col>
                    <v-col cols="2" align-self="center" class="text-center">
                        <v-btn text>
                            <v-icon small>mdi-react</v-icon>
                            <span>React</span>
                        </v-btn>
                    </v-col>
                    <v-col cols="2" align-self="center" class="text-center">
                        <v-btn text>
                            <v-icon small>mdi-vuejs</v-icon>
                            <span>Vue</span>
                        </v-btn>
                    </v-col>
                    <v-col cols="2" align-self="center" class="text-center">
                        <v-btn text>
                            <v-icon small>mdi-language-css3</v-icon>
                            <span>Css</span>
                        </v-btn>
                    </v-col>
                    <v-col cols="2" align-self="center" class="text-center">
                        <v-btn text>
                            <v-icon small>mdi-web</v-icon>
                            <span>Web</span>
                        </v-btn>
                    </v-col>
                    <v-col cols="2" align-self="center" class="text-center">
                        <v-btn text>
                            <v-icon small>mdi-language-java</v-icon>
                            <span>Java</span>
                        </v-btn>
                    </v-col>
                </v-row>
            </v-container>
        </v-content>
    </v-app>
</template>

<script>

    export default {
        name: 'App',

        data: () => ({
            drawer: null,
        }),
    };
</script>

<style>
    #hand_of_midas .v-navigation-drawer__border {
        display: none;
    }
</style>
