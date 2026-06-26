<script setup lang="ts">
import { Button } from 'primevue';
const mapsLink = 'https://maps.app.goo.gl/57URmX8binV3LXAe6';

const handleClickMaps = () => {
  window.open(mapsLink, '_blank');
};
</script>

<template>
  <Button
    label="Ver no Maps"
    icon="pi pi-map-marker"
    icon-pos="left"
    severity="success"
    outlined
    style="width: 100%"
    @click="handleClickMaps"
  />
</template>
