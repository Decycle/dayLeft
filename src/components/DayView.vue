<template>
    <h1 id="daysLeft">{{ daysLeft }} Days Left</h1>
</template>

<script>
import dayjs from "dayjs";

export default {
    name: "DayView",
    props: {
        date: Object,
    },
    computed: {
        daysLeft() {
            const today = dayjs();
            return this.date.diff(today, "days");
        },
    },
};
</script>

<style>
#daysLeft {
    font-size: 4rem;
    color: white;
    white-space: nowrap;
}
</style>
