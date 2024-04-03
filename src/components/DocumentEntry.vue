<script setup>
import { defineProps } from 'vue';

const props = defineProps(["title","date"]);
const docTitle = props.title;
const docDate = props.date;
</script>

<template>
<div>
    <h4>{{ docTitle }}</h4>
    <div>{{ docDate }}</div>
</div>
</template>

<style scoped>
div > div {
    text-align: right;
}
</style>