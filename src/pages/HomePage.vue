<script lang="ts" setup>
import WhatsAppButton from '@/components/WhatsAppButton.vue';
import TitleH1 from '@/components/typography/TitleH1.vue';
import SubtitleH3 from '@/components/typography/SubtitleH3.vue';
import TitleH2 from '@/components/typography/TitleH2.vue';
import IconDetail from '@/components/IconDetail.vue';
import TitleH3 from '@/components/typography/TitleH3.vue';

import Pictures from '@/assets/photos';
import PhotosGallery from '@/components/PhotosGallery.vue';
import MapWidget from '@/components/MapWidget.vue';
import MapsButton from '@/components/MapsButton.vue';
import CheckDetail from '@/components/CheckDetail.vue';
import LocationDetail from '@/components/LocationDetail.vue';

const subtitle = 'Chácara das Flores 2 • Jundiaí/SP';

const PicturesItems = Object.values(Pictures).map((picture, index) => ({
  itemImageSrc: picture,
  thumbnailImageSrc: picture,
  alt: `Apartamento à venda - Foto ${index + 1}`,
}));
</script>

<template>
  <section class="home-page">
    <TitleH1>Apartamento à Venda</TitleH1>
    <SubtitleH3>
      <i class="pi pi-map-marker" style="color: var(--p-primary-color); margin-right: 0.25rem" />
      {{ subtitle }}
    </SubtitleH3>
    <TitleH2>R$ 380.000,00</TitleH2>

    <div class="icon-details">
      <IconDetail icon="pi pi-expand" title="54m²" subtitle="Área privativa" />
      <IconDetail icon="pi pi-home" title="2" subtitle="Quartos" />
      <IconDetail icon="pi pi-map" title="1" subtitle="Banheiro" />
      <IconDetail icon="pi pi-car" title="1" subtitle="Vaga" />
    </div>
    <WhatsAppButton />

    <TitleH3>Fotos do apartamento</TitleH3>
    <PhotosGallery :items="PicturesItems" />
    <TitleH3>Sobre o apartamento</TitleH3>
    <TitleH3>Localização</TitleH3>
    <div class="home-page__location">
      <div class="home-page__location__details">
        <LocationDetail>
          Av. Comend. Gumercindo Barranqueiros, 70
          <br />
          Jardim Santa Teresa, Jundiaí - SP
        </LocationDetail>
        <CheckDetail>Próximo a escolas e supermercados</CheckDetail>
        <CheckDetail>Ao lado da Rodovia Anhanguera</CheckDetail>
        <CheckDetail>25 minutos de São Paulo</CheckDetail>
        <CheckDetail>5 minutos do centro de Jundiaí</CheckDetail>
        <MapsButton class="home-page__location__maps-button" />
      </div>
      <MapWidget />
    </div>
    <TitleH3>Prefere negociar por imobiliária?</TitleH3>
  </section>
</template>

<style lang="scss">
.home-page {
  display: flex;
  flex-direction: column;
  margin: 0 auto;

  @media (min-width: 768px) {
    padding: 2rem 1rem;
  }

  &__location {
    display: flex;
    flex-direction: column;
    gap: 1rem;
    margin-bottom: 2rem;

    @media (min-width: 768px) {
      flex-direction: row;
      align-items: center;
      justify-content: space-between;
    }

    &__details {
      display: flex;
      flex-direction: column;
      gap: 16px;
      min-width: 300px;
    }
    &__maps-button {
      margin-top: 32px;
    }
  }
}
.icon-details {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  padding: 1rem;
  gap: 3rem;
  @media (min-width: 768px) {
    grid-template-columns: repeat(4, 1fr);
  }
}
</style>
