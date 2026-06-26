<script lang="ts" setup></script>

<template>
  <div class="check-detail">
    <i class="pi pi-verified" style="color: var(--p-primary-color); margin-right: 1rem" />
    <b><slot /></b>
  </div>
</template>

<style lang="scss">
.check-detail {
  display: flex;
  align-items: center;
}
</style>
