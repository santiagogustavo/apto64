<script lang="ts" setup>
import { Galleria } from 'primevue';
import { ref } from 'vue';

defineProps({
  items: {
    type: Array,
    required: true,
  },
});

const activeIndex = ref(0);
const responsiveOptions = ref([
  {
    breakpoint: '1024px',
    numVisible: 5,
  },
  {
    breakpoint: '768px',
    numVisible: 3,
  },
  {
    breakpoint: '560px',
    numVisible: 1,
  },
]);
const displayCustom = ref(false);

const imageClick = (index: number) => {
  activeIndex.value = index;
  displayCustom.value = true;
};
</script>

<template>
  <div class="photos-gallery">
    <Galleria
      v-model:activeIndex="activeIndex"
      v-model:visible="displayCustom"
      :value="items"
      :responsiveOptions="responsiveOptions"
      containerStyle="max-width: 850px"
      :circular="true"
      :fullScreen="true"
      :showItemNavigators="true"
      :showThumbnails="false"
    >
      <template #item="slotProps">
        <img
          class="photo-gallery_current-image"
          :src="slotProps.item.itemImageSrc"
          :alt="slotProps.item.alt"
        />
      </template>
      <template #thumbnail="slotProps">
        <img
          :src="slotProps.item.thumbnailImageSrc"
          :alt="slotProps.item.alt"
          style="display: block"
        />
      </template>
    </Galleria>

    <div v-if="items" class="galleria-small-thumbnails__container">
      <div v-for="(image, index) of items" :key="String((image as any).alt)" class="col-span-4">
        <img
          :src="(image as any).thumbnailImageSrc"
          :alt="(image as any).alt"
          class="galleria-small-thumbnails__thumbnail"
          @click="imageClick(index)"
        />
      </div>
    </div>
  </div>
</template>

<style lang="scss">
.photo-gallery_current-image {
  width: 100%;
  height: 100%;
  object-fit: cover;
}
.galleria-small-thumbnails {
  &__container {
    margin: auto;
    max-width: fit-content;
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 1rem;
    overflow: hidden;
    @media (min-width: 768px) {
      grid-template-columns: repeat(3, 1fr);
    }
    @media (min-width: 1024px) {
      grid-template-columns: repeat(5, 1fr);
    }
  }
  &__thumbnail {
    cursor: pointer;
    width: 156px;
    height: 128px;
    object-fit: cover;
    border-radius: 8px;
    overflow: hidden;
  }
}
</style>
