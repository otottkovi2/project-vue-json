<script setup>
import DocumentEntry from '../components/DocumentEntry.vue';
import {ref,onMounted} from 'vue'
import Axios from 'axios'

const docs = ref([])

onMounted(() => {
  
  Axios.get("http://localhost:3000/docs").then(r => docs.value = r.data)

})

</script>

<template>
  <header>
    <h1>
      Dokumentumok
    </h1>
  </header>
  <main>
    <DocumentEntry v-for="doc in docs" v-bind:title="doc.title" v-bind:date="doc.date" />
  </main>
</template>
