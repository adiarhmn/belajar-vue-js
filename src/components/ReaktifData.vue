<script setup lang="ts">
import { onUpdated, reactive, ref } from 'vue';

// Data Tunggal seperti string boolean number atau object
const nama = ref('Reaktif Data');
const input = ref('');


const details = reactive({
  nama: "Adi Aulia Rahman",
  umur: 22
})


function gantiNama() {
  nama.value = input.value
}

function tambahUmur() {
  details.umur++
}

function logData(data:string | number) {
  console.log('render ' + data)
  return data
}

onUpdated(() => {
  console.log("onUpdated")
})
</script>

<template>
  <h1>{{ nama }}</h1>
  <input v-model="input" type="text" />
  <button @click="gantiNama()">
    Ganti nama
  </button>

  <div>
    <p>{{ logData(details.nama) }}</p>
    <p>{{ logData(details.umur) }}</p>
  </div>

  <button @click="tambahUmur()">
    Tambah Umur
  </button>

</template>
