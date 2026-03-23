<script setup lang="ts">
import { ref } from 'vue';


const nama = ref('Reaktif Data');
const input = ref('')

function gantiNama() {
  nama.value = input.value
}
</script>

<template>
  <h1>{{ nama }}</h1>
  <input v-model="input" type="text">
    <button @click="gantiNama()">
      Ganti nama
    </button>
</template>
