<template>
    <v-container class="px-0">
        <v-card elevation="2">
            <v-list-item>
                <v-list-item-content>
                    <v-checkbox v-model="checkbox1" :label="2021" ></v-checkbox>
                </v-list-item-content>
                <v-list-item-content>
                    <v-checkbox v-model="checkbox2" :label="2022"></v-checkbox>
                </v-list-item-content>
                <v-list-item-content>
                    <v-checkbox v-model="checkbox3" :label="2023"></v-checkbox>
                </v-list-item-content>
            </v-list-item>  
        </v-card>
        <v-card>
            <yearCard v-if="checkbox1" />
        </v-card>
        <v-card>
            <yearCard v-if="checkbox2" />
        </v-card>
        <v-card>
            <yearCard v-if="checkbox3" />
        </v-card>
    </v-container>
</template>

<script>
import yearCard from "./yearCard";
export default {
    name: "selectYear",
    components: {
        yearCard,
    },
    data() {
        return {
            name: "vishwas",
            checkbox1: false,
            checkbox2: false,
            checkbox3: false,
        };
    },
};
</script>
