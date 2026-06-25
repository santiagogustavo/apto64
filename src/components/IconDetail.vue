<script lang="ts" setup>
defineProps<{
  icon: string;
  title: string;
  subtitle: string;
}>();
</script>

<template>
  <div class="icon-detail">
    <i :class="icon" style="color: var(--p-primary-color)" />
    <span class="icon-detail__title">{{ title }}</span>
    <span class="icon-detail__subtitle">{{ subtitle }}</span>
  </div>
</template>

<style lang="scss">
.icon-detail {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  justify-content: center;
  width: fit-content;
  gap: 0.25rem;

  i {
    font-size: 1.25rem;
  }

  &__title {
    font-size: 1.25rem;
    font-weight: bold;
  }
  &__subtitle {
    font-size: 0.875rem;
    color: var(--p-text-secondary-color);
  }
}
</style>
