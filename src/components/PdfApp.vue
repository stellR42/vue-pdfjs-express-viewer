<script setup lang="ts">
import PDFJSExpress from "@pdftron/pdfjs-express-viewer";
import { onMounted, ref, watch } from "vue";

const props =
  defineProps<{ src: File | Blob; licenseKey: string; assetPath: string }>();

const viewer = ref();
const viewInstance = ref();
watch(
  [() => props.src],
  () => {
    if (viewInstance.value && props.src) {
      // console.log(viewInstance.value)
      viewInstance.value.UI.loadDocument(props.src, { filename: "myfile.pdf" });
    }
  },
  { immediate: true }
);
onMounted(() => {
  PDFJSExpress(
    {
      path: props.assetPath,
      licenseKey: props.licenseKey,
    },
    viewer.value
  ).then((instance) => {
    viewInstance.value = instance;
  });
});
</script>

<template>
  <div style="height: 100vh" ref="viewer"></div>
</template>
