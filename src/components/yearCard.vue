<template>
    <v-app min-height="10vh" >
       
            <v-container min-height="10vh">
                <v-select
                    :items="items"
                    label="Select Month"
                    @change="select_value"
                    solo
                ></v-select>

                <term1 v-if="val === 0"></term1>
                <term2 v-if="val === 1"></term2>
                <term3 v-if="val === 2"></term3>
            </v-container>
     
    </v-app>
</template>

<script>
import term1 from "./term1.vue";
import term2 from "./term2.vue";
import term3 from "./term3.vue";
export default {
    data() {
        return {
            select_month: "",
            val: -1,
            items: ["Jan - Apr", "May - Aug", "Sep - Dec"],
        };
    },
    components: {
        term1,
        term2,
        term3,
    },
    methods: {
        select_value(e) {
            if (e === "Jan - Apr") this.val = 0;
            if (e === "May - Aug") this.val = 1;
            if (e === "Sep - Dec") this.val = 2;
            console.log(e);
        },
    },
};
</script>

<style scoped lang="scss">
 ::v-deep .v-application--wrap {
    min-height: 10vh;
  }
</style>