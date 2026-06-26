<script lang="ts" setup></script>

<template>
  <div class="location-detail">
    <i class="pi pi-map" style="margin-right: 1rem" />
    <b><slot /></b>
  </div>
</template>

<style lang="scss" scoped>
.location-detail {
  display: flex;
  align-items: center;
}
b {
  font-weight: bold;
}
</style>
