<template>
    <v-container>
        <v-row>
            <v-text-field
                label="MAY"
                type="number"
                @change="disable1"
                v-model="val1"
                :disabled="disableFirst == true"
                outlined
            ></v-text-field>
            <v-text-field
                label="JUN"
                type="number"
                @change="disable2"
                :disabled="disableSecond == true"
                v-model="val2"
                outlined
            ></v-text-field>
            <v-text-field
                label="JUL"
                type="number"
                @change="disable3"
                :disabled="disableThird == true"
                v-model="val3"
                outlined
            ></v-text-field>
            <v-text-field
                label="AUG"
                type="number"
                @change="disable4"
                :disabled="disableFourth == true"
                v-model="val4"
                outlined
            ></v-text-field>
        </v-row>
        <v-row>
            <v-col>
                <div class="my-2">
                    <v-btn color="blue" dark @click="updateVal">
                        Calculate
                    </v-btn>
                </div>
            </v-col>
            <v-col>
                <div class="my-2">
                    <v-btn color="blue" dark @click="resetAll"> Reset </v-btn>
                </div>
            </v-col>
        </v-row>
    </v-container>
</template>

<script>
export default {
    name: "termFirst",
    data() {
        return {
            name: "vishwas",
            disableFirst: false,
            disableSecond: false,
            disableThird: false,
            disableFourth: false,
            gval: 0,
            val1: 0,
            val2: 0,
            val3: 0,
            val4: 0,
        };
    },
    methods: {
        updateVal() {
            this.val1 = this.disableFirst
                ? parseInt(this.gval, 10) + Math.ceil(Math.random() * 100)
                : this.val1;
            this.val2 = this.disableSecond
                ? parseInt(this.gval, 10) + Math.ceil(Math.random() * 100)
                : this.val2;
            this.val3 = this.disableThird
                ? parseInt(this.gval, 10) + Math.ceil(Math.random() * 100)
                : this.val3;
            this.val4 = this.disableFourth
                ? parseInt(this.gval, 10) + Math.ceil(Math.random() * 100)
                : this.val4;
            this.disableFirst = false;
            this.disableSecond = false;
            this.disableThird = false;
            this.disableFourth = false;
        },
        disable1(value) {
            this.disableSecond = true;
            this.disableThird = true;
            this.disableFourth = true;
            this.gval = value;
            console.log("clicked JAn");
            console.log(this.disableSecond);
            console.log(value);
        },
        disable2(value) {
            this.disableFirst = true;
            this.disableThird = true;
            this.disableFourth = true;
            this.gval = value;
        },
        disable3(value) {
            this.gval = value;

            this.disableSecond = true;
            this.disableFirst = true;
            this.disableFourth = true;
        },
        disable4(value) {
            this.gval = value;

            this.disableSecond = true;
            this.disableThird = true;
            this.disableFirst = true;
        },
        getStatus1() {
            return this.disableFirst === "true";
        },
        getStatus2() {
            return this.disableSecond === "true";
        },
        getStatus3() {
            return this.disableThird === "true";
        },
        getStatus4() {
            return this.disableFourth === "true";
        },
        resetAll() {
            this.val1 = 0;
            this.val2 = 0;
            this.val3 = 0;
            this.val4 = 0;
            this.gval = 0;
        },
    },
};
</script>
