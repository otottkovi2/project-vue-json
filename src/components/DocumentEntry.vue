<script setup>
import { defineProps } from 'vue';

const props = defineProps(["title","date","contentStart"]);
const docTitle = props.title;
const docDate = props.date;
const docContent = props.contentStart;
</script>

<template>
<div>
    <h4>{{ docTitle }}</h4>
    <h6>{{ docContent }}</h6>
    <div>{{ docDate }}</div>
</div>
<hr>
</template>

<style scoped>
div > div {
    text-align: right;
}
</style>