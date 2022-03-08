<script setup lang="ts">
import { ref } from 'vue';
import PdfApp from './components/PdfApp.vue';

const licenseKey= import.meta.env.LICENSE_KEY;
const file = ref()
function onFileChange(e) {
  const files = e.target.files[0];
  file.value = files;
}
</script>
<template>
  <input type="file" @change="onFileChange" />
  <button></button>
  <pdf-app :src="file" :license-key="licenseKey" asset-path="/pdfjs-express"></pdf-app>
</template>
