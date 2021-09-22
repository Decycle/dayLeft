<template>
    <div class="date-select">
        <div class="date-select-btn-container">
            <button class="date-preset-btn" @click="selectDate('2023-08-10')">
                🎂
            </button>
            <button class="date-preset-btn" @click="selectDate('2021-12-17')">
                ❄️
            </button>
        </div>
        <input
            type="date"
            id="trackDate"
            name="trackDate"
            @keyup.enter="selectDate($event.target.value)"
        />
    </div>
</template>

<script>
export default {
    emits: ["date-select"],
    methods: {
        selectDate(date) {
            this.$emit("date-select", date);
        },
    },
};
</script>

<style>
.date-select-btn-container {
    display: flex;
    justify-content: right;
}

#trackDate {
    font-size: 3rem;
    background-color: transparent;
    border: none;
    color: white;
}

.date-preset-btn {
    outline: none;
    background-color: transparent;
    border: none;
    font-size: 2.5rem;
}
</style>
