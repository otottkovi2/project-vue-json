<script setup>
import {ref} from 'vue'
import Axios from 'axios'

const newDoc = ref({id:null,title:null,content:null,date:null})
const submit = () => {
    const doc = newDoc
    let id = 0;
    Axios.get("http://localhost:3000/docs").then(r => id = r.data.length)
    doc.value.id = id
    doc.value.date = new Date().toISOString().split('T')[0];
    Axios.post("http://localhost:3000/docs",doc.value).then(r => alert(r.status == 201 ? "Dokumentum sikeresen mentve!" :
    "Hiba történt a dokumentum mentése során."))
}
</script>

<template>
<header>
    <h1>Új dokumentum</h1>
</header>
<main>
    <input type="text" v-model="newDoc.title" placeholder="title" />
    <textarea placeholder="write some text here..." v-model="newDoc.content"></textarea>
    <button @click="submit">Mentés</button>
</main>
</template>

<style scoped>
main{
    display: flex;
    flex-direction: column;
    justify-content: space-around;
    align-items: flex-start;
    height: 80vh;
    width: 90vw;
}
textarea {
    width: 80vw;
    height: 60vh;
}
button {
    margin-left: 1em;
    width: 10%;
    min-width: 7rem;
}
</style>