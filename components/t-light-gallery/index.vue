<template>
    <div class="mb-15 m t-8 mx-auto flex h-full md:max-w-6xl">
      <lightgallery
        :settings="{
          speed: 500,
          plugins: plugins,
          licenseKey: '0000-0000-000-0000',
        }"
      >
        <a
          v-for="image in images"
          :key="image.id"
          :data-src="image.url"
          :data-lg-size="image.width + '-' + image.height"
        >
          <img :id="image.id" :src="image.url" :alt="image.name" />
        </a>
      </lightgallery>
    </div>
  </template>
  
  <script lang="ts" setup>
  import Lightgallery from 'lightgallery/vue'
  import lgThumbnail from 'lightgallery/plugins/thumbnail'
  import lgZoom from 'lightgallery/plugins/zoom'
  
  const plugins = ref([lgThumbnail, lgZoom])
  
  const images = [
    {
      url: 'https://dev.media.er2.co/es/asturias/61dac18b48b99/750/63c92955946d2.jpg',
      height: 200,
      width: 200,
      id: 33,
      name: 'bla',
    },
  ]
  </script>
  
  <style lang="css" scoped>
  @import 'lightgallery/css/lightgallery.css';
  @import 'lightgallery/css/lg-thumbnail.css';
  @import 'lightgallery/css/lg-zoom.css';
  </style>
  