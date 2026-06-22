<script lang="ts" setup>
import WhatsAppButton from '@/components/WhatsAppButton.vue';
import TitleH1 from '@/components/typography/TitleH1.vue';
import SubtitleH3 from '@/components/typography/SubtitleH3.vue';
import TitleH2 from '@/components/typography/TitleH2.vue';
</script>

<template>
  <section>
    <TitleH1>Apartamento à Venda</TitleH1>
    <SubtitleH3
      ><i class="pi pi-map-marker" style="color: var(--p-primary-color)" /> Chácara das flores -
      Jundiaí/SP</SubtitleH3
    >
    <TitleH2>R$ 380.000,00</TitleH2>
    <WhatsAppButton />
  </section>
</template>
