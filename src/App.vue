<template>
    <DateSelect v-if="!selectedDate" @date-select="selectDate" />
    <div v-else>
        <DayView :date="selectedDate" />
        <button class="btn" @click="clearDate">Back</button>
    </div>
</template>

<script>
import dayjs from "dayjs";
import DayView from "./components/DayView.vue";
import DateSelect from "./components/DateSelect.vue";

export default {
    name: "App",
    data() {
        return {
            selectedDate: null,
        };
    },
    components: {
        DayView,
        DateSelect,
    },
    methods: {
        selectDate(date) {
            this.selectedDate = dayjs(date);
        },
        clearDate() {
            this.selectedDate = null;
        },
    },
};
</script>

<style>
body {
    background-color: #97372e;
    font-family: "helvetica Neue", Helvetica, Arial;
}

#app {
    position: fixed;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    margin: 0;
    border: 0;
}

.btn {
    outline: none;
    border: 2px white solid;
    background-color: transparent;
    color: white;
    font-size: 2rem;
}
</style>
