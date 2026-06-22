<script setup lang="ts">
import { Button } from 'primevue';
const messageLink = 'https://wa.me/5511973199192';

const handleClickWhatsapp = () => {
  window.open(messageLink, '_blank');
};
</script>

<template>
  <Button
    label="Conversar no WhatsApp"
    icon="pi pi-whatsapp"
    icon-pos="left"
    severity="success"
    @click="handleClickWhatsapp"
  />
</template>
