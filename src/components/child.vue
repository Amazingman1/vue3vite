<template>

  <div>
    <h1>Child Component</h1>
    <button @click="sendData">Send Data to Parent</button>
  </div>
</template>


<script setup lang="ts">
import { defineEmits } from 'vue'

const sendData = () => {
  defineEmits(["send-data"]);
}
</script>