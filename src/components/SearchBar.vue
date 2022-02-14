<template> 
<section class="text-white fs-4">
    <select v-model="selectedOption" @change="changeOption" class="ms-1">
        <option value="">{{ placeholder || 'Choose an Option:' }}</option>
        <option v-for="(option, index) in options" :key="option.id || index">{{ option }}</option>
    </select>
</section>
</template>

<script>
export default {
    name: 'SearchBar',
    props: ["placeholder", "options"],
    data() {
        return {
            selectedOption: "",
        };
    },
    methods: {
        changeOption() {
            this.$emit("change-option", this.selectedOption);
        }
    },
}
</script>

<style lang="scss" scoped>
@import '../assets/scss/style.scss';
select {
    border: 2px solid #fff;
    background-color: $main-color;
    color: #fff;
}
</style>